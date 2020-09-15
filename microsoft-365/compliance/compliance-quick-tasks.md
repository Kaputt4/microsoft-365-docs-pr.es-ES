---
title: Tareas rápidas para empezar a usar el Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Obtenga información sobre las tareas que le ayudarán a empezar a trabajar rápidamente con el cumplimiento en Microsoft 365.
ms.openlocfilehash: 1702c05b271c0e8b5456c1a93f8bf1dc28f7fbd9
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816819"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Tareas rápidas para empezar a usar el Centro de cumplimiento de Microsoft 365

Si no está familiarizado con el cumplimiento de Microsoft 365 y se pregunta dónde empezar, en este artículo se proporcionan instrucciones sobre los conceptos básicos y se establecen las prioridades de las tareas de cumplimiento importantes. Este artículo le ayudará a empezar rápidamente con la administración y supervisión de los datos, la protección de la información y la minimización de los riesgos de Insider.

Este artículo también es útil si está intentando administrar los riesgos, proteger sus datos y seguir cumpliendo con las normativas y los estándares con una nueva plantilla de personal remoto. Los empleados ahora están colaborando y conectándose entre sí de nuevas formas, y esto significa que es posible que los procesos de cumplimiento y los controles existentes se adapten. La identificación y la administración de estos nuevos riesgos de cumplimiento en su organización es fundamental para proteger sus datos y minimizar las amenazas y los riesgos.

Una vez que haya completado estas tareas básicas de cumplimiento, considere la posibilidad de expandir la cobertura de cumplimiento en su organización mediante la implementación de soluciones de cumplimiento adicionales de Microsoft 365.

## <a name="task-1-configure-compliance-permissions"></a>Tarea 1: configurar permisos de cumplimiento

Es importante administrar quién en su organización tiene acceso al centro de cumplimiento de Microsoft 365 para ver el contenido y realizar tareas de administración. Microsoft 365 proporciona roles administrativos específicos para el cumplimiento y el uso de las herramientas incluidas en el centro de cumplimiento de Microsoft 365.

Empiece por asignar los permisos de cumplimiento a los miembros de la organización para que puedan realizar estas tareas y evitar que personas no autorizadas tengan acceso a áreas ajenas a sus responsabilidades. Querrá asegurarse de que ha asignado a las personas adecuadas al administrador de datos de **cumplimiento** y a los roles de administrador de **Administrador de cumplimiento** antes de empezar a configurar e implementar soluciones de cumplimiento incluidas con Microsoft 365. También necesitará asignar usuarios al rol de lector global de Azure Active Directory para ver los datos con la puntuación de cumplimiento.

Para obtener instrucciones paso a paso para configurar permisos y asignar personas a roles de administrador, consulte [Permissions in the Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Tarea 2: conocer el estado de cumplimiento

Es difícil saber a dónde ir si no sabes dónde estás. Satisfacer sus necesidades de cumplimiento de normas incluye comprender el nivel de riesgo actual y las actualizaciones que se necesitan en cada vez que cambien horas. Independientemente de si su organización es nueva en los requisitos de cumplimiento o tiene una experiencia profunda con los estándares y las regulaciones que rigen a la industria, lo mejor que puede hacer para mejorar el cumplimiento es comprender dónde se encuentra su organización.

La [puntuación de cumplimiento de Microsoft](compliance-score.md) puede ayudarle a comprender la postura de cumplimiento normativo y las áreas de resaltado de su organización que pueden necesitar mejora. La puntuación de cumplimiento usa un panel centralizado para calcular una puntuación basada en riesgos, lo que mide su progreso en la realización de acciones que ayudan a reducir los riesgos relacionados con la protección de datos y los estándares normativos. También puede usar la puntuación de cumplimiento como una herramienta para realizar un seguimiento de todas las evaluaciones de riesgos. Proporciona funcionalidades de flujo de trabajo para ayudarle a completar eficazmente las evaluaciones de riesgos mediante una herramienta común.

Para obtener instrucciones paso a paso sobre cómo empezar a utilizar la puntuación de cumplimiento, consulte [set up Compliance score](compliance-score-setup.md).

>[!IMPORTANT]
>La seguridad y el cumplimiento están estrechamente integrados en la mayoría de las organizaciones. Es importante que la organización se base en la seguridad básica, la protección contra amenazas y las áreas de administración de identidades y acceso para ayudar a proporcionar un enfoque de defensa en profundidad tanto para la seguridad como para el cumplimiento.
>
>Compruebe la [puntuación segura de microsoft 365](../security/mtp/microsoft-secure-score.md) en el centro de seguridad de Microsoft 365 y complete las tareas descritas en los siguientes artículos:
>
> - [Plan de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá](../security/office-365-security/security-roadmap.md)
> - [Las 12 principales tareas para que los equipos de seguridad admitan el trabajo desde casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarea 3: habilitar la auditoría para su organización

Ahora que ha determinado el estado actual de su organización y quién puede administrar las funciones de cumplimiento, el siguiente paso consiste en asegurarse de que tiene los datos para realizar las investigaciones de cumplimiento y generar informes para las actividades de red y usuario en su organización. La habilitación de la auditoría también es un requisito previo importante para las soluciones de cumplimiento que se tratan más adelante en este artículo.

La información que proporciona el registro de auditoría es una herramienta valiosa para ayudar a adecuar los requisitos de cumplimiento a soluciones que puedan ayudarle a administrar y supervisar las áreas de cumplimiento que necesitan mejora. El registro de auditoría debe estar habilitado antes de que se registren las actividades y antes de que pueda buscar en el registro de auditoría. Cuando está habilitada, la actividad de usuario y de administrador de su organización se registra en el registro de auditoría y se conserva durante 90 días, y hasta un año, según la licencia asignada a los usuarios.

Para obtener instrucciones paso a paso para activar la auditoría, vea [activar o desactivar la búsqueda de registros de auditoría](turn-audit-log-search-on-or-off.md).

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarea 4: crear directivas para avisarle sobre posibles problemas de cumplimiento

Microsoft proporciona varias directivas de alerta integradas que ayudan a identificar los permisos de administrador abusos, la actividad de malware, las posibles amenazas externas e internas y los riesgos del gobierno de la información. Estas directivas están activadas de forma predeterminada, pero es posible que deba configurar alertas personalizadas para ayudar a administrar los requisitos de cumplimiento específicos de su organización.

Use las directivas de alerta y las herramientas del escritorio para crear directivas de alertas personalizadas y ver las alertas generadas cuando los usuarios realizan actividades que coinciden con las condiciones de la Directiva. Algunos ejemplos podrían ser usar directivas de alerta para realizar un seguimiento de las actividades de usuario y de administrador que afectan a los requisitos de cumplimiento, los permisos y los incidentes de pérdida de datos de la organización.

Para obtener instrucciones paso a paso para crear directivas de alertas personalizadas, consulte [Alert policies en el centro de seguridad y cumplimiento](alert-policies.md).

## <a name="task-5-configure-just-in-time-access-for-your-administrators"></a>Tarea 5: configurar el acceso Just-in-Time para los administradores

Tener acceso permanente a algunos usuarios a la información confidencial o a la configuración de la red crítica es una posible vía para las actividades en peligro o para las actividades de amenazas internas. La [Administración de acceso con privilegios](privileged-access-management-overview.md) ayuda a proteger la organización de las infracciones y ayuda a cumplir los procedimientos recomendados al limitar el acceso permanente a los datos confidenciales o el acceso a las opciones de configuración fundamentales. En lugar de que los administradores tengan acceso constante, las reglas de acceso Just-in-Time se implementan para las tareas que necesitan permisos elevados. La habilitación de la administración de acceso privilegiada en Microsoft 365 permite que su organización opere con privilegios que no tienen ningún derecho y proporciona un nivel de defensa contra las vulnerabilidades de acceso administrativo.

Para obtener instrucciones paso a paso para configurar la administración del acceso con privilegios, consulte [Get Started with privileged Access Management](privileged-access-management-configuration.md). Para obtener información sobre las licencias de administración de acceso privilegiadas, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#privileged-access-management-in-office-365).

## <a name="task-6-classify-and-protect-sensitive-data"></a>Tarea 6: clasificar y proteger los datos confidenciales

Para realizar su trabajo, las personas de su organización colaboran con otras tanto dentro como fuera de la organización. Esto significa que el contenido ya no se queda detrás de un firewall, sino que puede desplazarse a todas partes, a través de dispositivos, aplicaciones y servicios. Y cuando se desplaza, usted quiere que lo haga de una forma segura y protegida que cumpla con las directivas empresariales y de cumplimiento de normas de su organización.

Las [etiquetas de confidencialidad](sensitivity-labels.md) le permiten clasificar y proteger los datos de su organización, al tiempo que garantizan que no se obstaculice la productividad del usuario y su capacidad de colaboración. Usar las etiquetas de confidencialidad para exigir el cifrado y las restricciones de uso aplique los marcadores visuales y proteja la información entre plataformas y dispositivos, local y en la nube.

Para obtener información paso a paso sobre cómo configurar y usar las etiquetas de confidencialidad, consulte Introducción [a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md). Para obtener información sobre la licencia de la etiqueta de confidencialidad, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-7-configure-a-retention-policy"></a>Tarea 7: configurar una directiva de retención

Una [Directiva de retención](retention.md) permite decidir de forma proactiva Si se conserva el contenido, se elimina el contenido o ambos, y, a continuación, se elimina el contenido al final de un período de retención especificado. Estas acciones pueden ser necesarias para cumplir con las regulaciones de la industria y las directivas internas, así como para reducir el riesgo en caso de litigio o de una violación de la seguridad.

Cuando el contenido está sujeto a una directiva de retención, los usuarios pueden seguir editando y trabajando con el contenido como si no cambiara nada. El contenido se conserva en su ubicación original. Pero si alguien edita o elimina contenido que está sujeto a la Directiva de retención, se guarda una copia del contenido original en una ubicación segura en la que se conserva mientras la Directiva de retención para ese contenido está en vigor.

Puede poner rápidamente una directiva de retención en su lugar para varias ubicaciones en su entorno de Microsoft 365, como correo de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365. No hay límites en cuanto al número de buzones o sitios que esta Directiva puede incluir automáticamente. Pero si necesita obtener más selectivo, puede hacerlo configurando una directiva de retención para ubicaciones específicas e incluya o excluya sitios o usuarios.

Para obtener instrucciones paso a paso para configurar una directiva de retención, consulte [Create and configure Retention Policies](create-retention-policies.md). Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).

## <a name="task-8-configure-sensitive-information-and-offensive-language-policies"></a>Tarea 8: configurar la información confidencial y las directivas de lenguaje ofensivo

La protección de la información confidencial y la detección y la actuación de los incidentes de acoso del lugar de trabajo es una parte importante del cumplimiento de las directivas y los estándares internos. El cumplimiento de la [comunicación](communication-compliance-feature-reference.md) en Microsoft 365 ayuda a minimizar estos riesgos al ayudarle a detectar, capturar y realizar acciones de corrección rápidamente para el correo electrónico y las comunicaciones de Microsoft Teams. Estos incluyen comunicaciones inadecuadas que contienen palabras soeces, amenazas y acoso y comunicaciones que comparten información confidencial dentro y fuera de la organización.

Una plantilla predefinida de directiva de directivas *antiacoser y de lenguaje ofensivo* le permite analizar las comunicaciones internas y externas de las coincidencias de directivas para que puedan examinarlas los revisores designados. Los revisores pueden investigar el correo electrónico explorado, Microsoft Teams, Yammer o las comunicaciones de terceros de la organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen con los estándares de la organización.

La plantilla de directiva de *información confidencial* predefinida le ayuda a crear rápidamente una directiva para analizar el correo electrónico y las comunicaciones de Microsoft teams que contienen palabras clave o tipos de información confidencial definidos para ayudar a garantizar que no se compartan datos importantes con personas que no tienen acceso. Estas actividades pueden incluir comunicación no autorizada sobre proyectos confidenciales o reglas específicas del sector sobre el comercio de Insider u otras actividades de colusión.

Para obtener instrucciones paso a paso para planear y configurar el cumplimiento de la comunicación, vea [Plan for Communication Compliance](communication-compliance-plan.md) y [Get Started with Communication Compliance](communication-compliance-configure.md). Para obtener información sobre las licencias de cumplimiento de comunicaciones, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-9-see-whats-happening-with-your-sensitive-items"></a>Tarea 9: ver lo que ocurre con sus elementos confidenciales

Las etiquetas de confidencialidad, los tipos de información confidencial, las etiquetas de retención y los clasificadores que se pueden entrenar pueden usarse para clasificar y etiquetar elementos confidenciales en Exchange, SharePoint y OneDrive, tal y como se ha visto en las tareas anteriores. El último paso en el recorrido rápido de la tarea es ver los elementos que se han etiquetado y las acciones que los usuarios toman sobre esos elementos confidenciales. Explorador de [contenido](data-classification-content-explorer.md) y [Explorador de actividades](data-classification-activity-explorer.md) proporcionan esta visibilidad.

### <a name="content-explorer"></a>Explorador de contenido
 El explorador de contenido le permite ver, en su formato nativo, todos los elementos que se han clasificado como un tipo de información confidencial o que pertenecen a una clasificación determinada por un clasificador capacitado, así como todos los elementos que tienen la etiqueta de confidencialidad o retención aplicada.

Para obtener instrucciones paso a paso sobre el uso del explorador de contenido, vea [conocer la información general de la clasificación](data-classification-overview.md)de datos y [Introducción al explorador de contenido](data-classification-content-explorer.md).

### <a name="activity-explorer"></a>Explorador de actividades
Activity Explorer le ayuda a supervisar lo que se está haciendo con los elementos confidenciales clasificados y etiquetados en:
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

Para obtener una guía paso a paso sobre el uso del explorador de actividades, consulte Introducción [a Activity Explorer](data-classification-activity-explorer.md).

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha configurado los conceptos básicos para la administración de cumplimiento para su organización, tenga en cuenta las siguientes soluciones de cumplimiento de Microsoft 365 para ayudarle a proteger la información confidencial y a detectar y actuar en riesgos de Insider adicionales.

### <a name="configure-retention-labels"></a>Configurar etiquetas de retención

Mientras que las directivas de retención se aplican en el nivel de contenedor a ubicaciones como sitios de SharePoint y buzones de Exchange, las [etiquetas de retención](retention.md#retention-labels) permiten una identificación más específica de las directivas de retención y eliminación. Por ejemplo, en el nivel de mensaje de correo electrónico o documento que los usuarios finales pueden aplicar manualmente, además de la aplicación automática por los administradores. También puede aplicar una etiqueta de retención a una biblioteca de documentos, una carpeta o un conjunto de documentos en SharePoint, para que todos los documentos que se almacenan en esa ubicación hereden la etiqueta de retención predeterminada.

Además, las etiquetas de retención admiten la [Administración de registros](records-management.md) para marcar contenido como registro. Cuando esto ocurre, la etiqueta coloca otras restricciones en el contenido que podría ser necesaria para ayudar a su organización a cumplir con los requisitos normativos.

Para obtener instrucciones paso a paso para crear y publicar etiquetas de retención, consulte las siguientes instrucciones:
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

Para empezar a trabajar con la administración de registros, consulte Introducción [a la administración de registros](get-started-with-records-management.md).

### <a name="identify-and-define-sensitive-information-types"></a>Identificación y definición de tipos de información confidencial

Definir los tipos de información confidencial basándose en el patrón contenido en la información de los datos de la organización. Usar [la información confidencial integrada los tipos](what-the-sensitive-information-types-look-for.md) ayudan a identificar y proteger los números de tarjetas de crédito, los números de cuentas bancarias, los números de pasaporte y mucho más. O bien, cree sus propios [tipos de información de confidencialidad personalizados](custom-sensitive-info-types.md) específicos de su organización.

Para obtener instrucciones paso a paso para definir tipos personalizados de información confidencial, vea [crear un tipo personalizado de información confidencial en el centro de seguridad & cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type).

### <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

[Las directivas de prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md) le permiten identificar, supervisar y proteger automáticamente la información confidencial de toda la organización de Microsoft 365. Use directivas de DLP para identificar elementos confidenciales en los servicios de Microsoft, impedir el uso compartido accidental de elementos confidenciales y ayudar a los usuarios a mantener la conformidad sin interrumpir su flujo de trabajo.

Para obtener información paso a paso sobre cómo configurar directivas de DLP, consulte Introducción a las [recomendaciones de directivas de DLP](get-started-with-dlp-policy-recommendations.md) y comenzar [a trabajar con la Directiva de DLP predeterminada](get-started-with-the-default-dlp-policy.md). Para obtener información sobre las licencias de administración de pérdida de datos, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="detect-and-act-on-insider-risks"></a>Detectar y actuar en los riesgos de Insider

Cada vez más, los empleados tienen un mayor acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos en toda la organización, a la vez que cumplen los requisitos de cumplimiento y los estándares de privacidad de los empleados. Estos riesgos pueden incluir el robo de datos al dejar en parte a los empleados y filtrar los datos de la información fuera de la organización mediante un uso compartido accidental o un propósito malintencionado.

La [Administración de riesgos de Insider](insider-risk-management-policies.md) de Microsoft 365 usa toda la amplitud de los indicadores de servicio y de terceros para ayudarle a identificar, clasificar y actuar con rapidez en la actividad de los usuarios arriesgados. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de Insider le permite definir directivas específicas para identificar los indicadores de riesgo y emprender acciones para mitigar estos riesgos.

Para obtener instrucciones paso a paso para planear y configurar directivas de administración de riesgos de Insider, vea [Plan for Insider Risk Management](insider-risk-management-plan.md) y [Get Started with Insider Risk Management](insider-risk-management-configure.md). Para obtener información sobre las licencias de administración de riesgos de Insider, vea [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).
