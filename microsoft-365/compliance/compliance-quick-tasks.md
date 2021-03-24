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
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Obtenga información sobre las tareas que le ayudarán a empezar rápidamente con el cumplimiento en Microsoft 365.
ms.openlocfilehash: b8a6f98a38dcb6096287cbc2389648c0e7457e5c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052108"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Tareas rápidas para empezar a usar el Centro de cumplimiento de Microsoft 365

Si es nuevo en el cumplimiento de Microsoft 365 y se pregunta dónde empezar, en este artículo se proporcionan instrucciones sobre los conceptos básicos y se priorizan las tareas de cumplimiento importantes. Este artículo le ayudará a empezar rápidamente a administrar y supervisar los datos, proteger la información y minimizar los riesgos de insider.

Este artículo también es útil si está averiguando la mejor manera de administrar riesgos, proteger sus datos y cumplir con las normativas y estándares con un personal recién remoto. Los empleados ahora colaboran y se conectan entre sí de nuevas maneras, lo que significa que es posible que los procesos y controles de cumplimiento existentes necesiten adaptarse. Identificar y administrar estos nuevos riesgos de cumplimiento dentro de la organización es fundamental para proteger los datos y minimizar las amenazas y riesgos.

Después de completar estas tareas básicas de cumplimiento, considere la posibilidad de ampliar la cobertura de cumplimiento en su organización implementando soluciones de cumplimiento de Microsoft 365 adicionales.

## <a name="task-1-configure-compliance-permissions"></a>Tarea 1: Configurar permisos de cumplimiento

Es importante administrar quién en su organización tiene acceso al Centro de cumplimiento de Microsoft 365 para ver contenido y realizar tareas de administración. Microsoft 365 proporciona roles administrativos específicos para el cumplimiento y para el uso de las herramientas incluidas en el Centro de cumplimiento de Microsoft 365.

Empiece asignando permisos de cumplimiento a las personas de su organización para que puedan realizar estas tareas y evitar que personas no autorizadas tengan acceso a áreas fuera de sus responsabilidades. Antes de empezar a configurar e implementar las soluciones  de cumplimiento  incluidas en Microsoft 365, querrá asegurarse de que ha asignado las personas adecuadas al administrador de datos de cumplimiento y a los roles de administrador de cumplimiento. También tendrá que asignar usuarios al rol de lector global de Azure Active Directory para ver los datos en el Administrador de cumplimiento.

Para obtener instrucciones paso a paso para configurar permisos y asignar personas a roles de administrador, vea Permisos en el Centro de [seguridad & cumplimiento](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Tarea 2: Conocer su estado de cumplimiento

Es difícil saber a dónde ir si no sabe dónde está. Satisfacer sus necesidades de cumplimiento incluye comprender su nivel actual de riesgo y qué actualizaciones pueden ser necesarias en estos tiempos cambiantes. Tanto si su organización es nueva en los requisitos de cumplimiento como si tiene una amplia experiencia con los estándares y normativas que rigen su sector, lo mejor que puede hacer para mejorar el cumplimiento es comprender dónde se encuentra su organización.

[Microsoft Compliance Manager](compliance-manager.md) puede ayudarle a comprender la posición de cumplimiento de su organización y destacar las áreas que pueden necesitar mejoras. El Administrador de cumplimiento usa un panel centralizado para calcular una puntuación basada en riesgos, que mide el progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos. También puede usar el Administrador de cumplimiento como herramienta para realizar un seguimiento de todas las evaluaciones de riesgos. Ofrece funciones de flujo de trabajo que le permiten completar de manera eficiente las evaluaciones de riesgos a través de una herramienta común.

Para obtener instrucciones paso a paso para empezar a trabajar con el Administrador de cumplimiento, vea [Introducción al Administrador de cumplimiento.](compliance-manager-setup.md)

>[!IMPORTANT]
>La seguridad y el cumplimiento están estrechamente integrados para la mayoría de las organizaciones. Es importante que su organización aborde la seguridad básica, la protección contra amenazas y las áreas de administración de identidad y acceso para ayudar a proporcionar un enfoque de defensa en profundidad tanto para la seguridad como para el cumplimiento.
>
>Compruebe la puntuación segura de [Microsoft 365](../security/defender/microsoft-secure-score.md) en el Centro de seguridad de Microsoft 365 y complete las tareas descritas en los siguientes artículos:
>
> - [Hoja de ruta de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá](../security/defender-365-security/security-roadmap.md)
> - [Las 12 tareas principales para que los equipos de seguridad admitan el trabajo desde casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarea 3: Habilitar la auditoría para su organización

Ahora que ha determinado el estado actual de su organización y quién puede administrar las funciones de cumplimiento, el siguiente paso es asegurarse de que tiene los datos para llevar a cabo investigaciones de cumplimiento y generar informes para las actividades de red y de usuario en su organización. Habilitar la auditoría también es un requisito previo importante para las soluciones de cumplimiento que se tratan más adelante en este artículo.

Los conocimientos proporcionados por el registro de auditoría son una herramienta valiosa para ayudar a cumplir los requisitos de cumplimiento con soluciones que pueden ayudarle a administrar y supervisar las áreas de cumplimiento que necesitan mejoras. El registro de auditoría debe habilitarse antes de que se registren las actividades y antes de poder buscar en el registro de auditoría. Cuando se habilita, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se retiene durante 90 días y hasta un año, según la licencia asignada a los usuarios.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del [registro de auditoría.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarea 4: Crear directivas para alertar sobre posibles problemas de cumplimiento

Microsoft proporciona varias directivas de alerta integradas que ayudan a identificar el uso indebido de permisos de administrador, la actividad de malware, las posibles amenazas externas e internas y los riesgos de gobierno de la información. Estas directivas están activadas de forma predeterminada, pero es posible que deba configurar alertas personalizadas para ayudar a administrar los requisitos de cumplimiento específicos de su organización.

Use las herramientas de directiva de alerta y panel de alertas para crear directivas de alerta personalizadas y ver las alertas generadas cuando los usuarios realizan actividades que coinciden con las condiciones de la directiva. Algunos ejemplos podrían ser usar directivas de alerta para realizar un seguimiento de las actividades de usuario y administrador que afectan a los requisitos de cumplimiento, los permisos y los incidentes de pérdida de datos en la organización.

Para obtener instrucciones paso a paso para crear directivas de alerta personalizadas, vea Directivas de alerta [en el Centro de seguridad y cumplimiento](alert-policies.md).

## <a name="task-5-classify-and-protect-sensitive-data"></a>Tarea 5: Clasificar y proteger datos confidenciales

Para realizar su trabajo, las personas de su organización colaboran con otras tanto dentro como fuera de la organización. Esto significa que el contenido ya no se queda detrás de un firewall, sino que puede desplazarse a todas partes, a través de dispositivos, aplicaciones y servicios. Y cuando se desplaza, usted quiere que lo haga de una forma segura y protegida que cumpla con las directivas empresariales y de cumplimiento de normas de su organización.

[Las etiquetas](sensitivity-labels.md) de confidencialidad le permiten clasificar y proteger los datos de su organización, al tiempo que se asegura de que la productividad del usuario y su capacidad de colaboración no se ve obstaculizada. Use etiquetas de confidencialidad para aplicar restricciones de cifrado y uso a los marcados visuales y proteger la información en plataformas y dispositivos, locales y en la nube.

Para obtener instrucciones paso a paso para configurar y usar etiquetas de confidencialidad, vea Introducción a [las etiquetas de confidencialidad.](get-started-with-sensitivity-labels.md) Para obtener información sobre licencias de etiquetas de confidencialidad, consulte Guía de licencias de [Microsoft 365 para la seguridad & cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-6-configure-a-retention-policy"></a>Tarea 6: Configurar una directiva de retención

Una [directiva de retención](retention.md) le permite decidir de forma proactiva si desea conservar contenido, eliminar contenido o ambos: conservar y eliminar el contenido al final de un período de retención especificado. Estas acciones pueden ser necesarias para cumplir con las normativas del sector y las directivas internas, así como reducir el riesgo en caso de litigio o una infracción de seguridad.

Cuando el contenido está sujeto a una directiva de retención, las personas pueden seguir editando y trabajando con el contenido como si nada hubiera cambiado. El contenido se conserva en su lugar, en su ubicación original. Pero si alguien edita o elimina contenido sujeto a la directiva de retención, se guarda una copia del contenido original en una ubicación segura donde se conserva mientras la directiva de retención de ese contenido está en vigor.

Puede establecer rápidamente una directiva de retención para varias ubicaciones en el entorno de Microsoft 365, como correo de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365. No hay límites en el número de buzones o sitios que esta directiva puede incluir automáticamente. Pero si necesita ser más selectivo, puede hacerlo configurando una directiva de retención para ubicaciones específicas e incluir o excluir sitios o usuarios.

Para obtener instrucciones paso a paso para configurar una directiva de retención, vea [Create and configure retention policies](create-retention-policies.md). Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y etiquetas de retención](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Tarea 7: Configurar la información confidencial y las directivas de lenguaje ofensivo

Proteger la información confidencial y detectar y actuar en incidentes de acoso en el lugar de trabajo es una parte importante del cumplimiento de las directivas y estándares internos. [El cumplimiento de](communication-compliance-feature-reference.md) las comunicaciones en Microsoft 365 ayuda a minimizar estos riesgos al ayudarle a detectar, capturar y realizar rápidamente acciones de corrección para el correo electrónico y las comunicaciones de Microsoft Teams. Entre ellas se incluyen comunicaciones inapropiadas que contienen palabras profanas, amenazas y hostigamiento y comunicaciones que comparten información confidencial dentro y fuera de su organización.

Una plantilla de  directiva contra acoso y lenguaje ofensivo predefinida permite examinar las comunicaciones internas y externas en busca de coincidencias de directivas para que puedan ser examinadas por revisores designados. Los revisores pueden investigar el correo electrónico escaneado, Microsoft Teams, Yammer o las comunicaciones de terceros de su organización y realizar las acciones de corrección adecuadas para asegurarse de que cumplen con los estándares de su organización.

La plantilla de  directiva de información confidencial predefinida le ayuda a crear rápidamente una directiva para examinar el correo electrónico y las comunicaciones de Microsoft Teams que contienen palabras clave o tipos de información confidencial definidos para asegurarse de que los datos importantes no se compartan con personas que no deberían tener acceso. Estas actividades pueden incluir comunicaciones no autorizadas sobre proyectos confidenciales o reglas específicas del sector sobre el comercio interno u otras actividades de connivencia.

Para obtener instrucciones paso a paso para planear y configurar el cumplimiento de comunicaciones, vea [Plan for communication compliance](communication-compliance-plan.md) y Get started with communication [compliance](communication-compliance-configure.md). Para obtener información sobre las licencias de cumplimiento de comunicaciones, vea Instrucciones de licencias de [Microsoft 365 para seguridad & cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Tarea 8: Ver lo que ocurre con los elementos confidenciales

Las etiquetas de confidencialidad, los tipos de información confidencial, las directivas y las etiquetas de retención y los clasificadores capacitados se pueden usar para clasificar y etiquetar elementos confidenciales en Exchange, SharePoint y OneDrive como se ha visto en las tareas anteriores. El último paso del recorrido rápido de la tarea es ver qué elementos se han etiquetado y qué acciones están llevando a cabo los usuarios en esos elementos confidenciales. [El explorador de](data-classification-content-explorer.md) contenido [y el explorador de actividades](data-classification-activity-explorer.md) proporcionan esta visibilidad.

### <a name="content-explorer"></a>Explorador de contenido
 El explorador de contenido le permite ver, en su formato nativo, todos los elementos que se han clasificado como un tipo de información confidencial o que pertenecen a una determinada clasificación por un clasificador capacitado, así como todos los elementos que tienen aplicada la etiqueta de confidencialidad o retención.

Para obtener instrucciones paso a paso sobre el uso del explorador de contenido, vea [Know your data - data classification overview](data-classification-overview.md)y Get started with content [explorer](data-classification-content-explorer.md).

### <a name="activity-explorer"></a>Explorador de actividad
El explorador de actividades le ayuda a supervisar lo que se está haciendo con los elementos confidenciales clasificados y etiquetados en:
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

Para obtener instrucciones paso a paso sobre cómo usar el explorador de actividades, vea [Introducción al explorador de actividades](data-classification-activity-explorer.md).

## <a name="next-steps"></a>Siguientes pasos

Ahora que ha configurado los conceptos básicos para la administración de cumplimiento para su organización, considere las siguientes soluciones de cumplimiento en Microsoft 365 para ayudarle a proteger la información confidencial y detectar y actuar en riesgos adicionales de insider.

### <a name="configure-retention-labels"></a>Configurar etiquetas de retención

Aunque las directivas de retención se aplican en el nivel de contenedor a ubicaciones como sitios de SharePoint y buzones de [Exchange,](retention.md#retention-labels) las etiquetas de retención permiten una orientación más específica para las directivas de retención y eliminación. Por ejemplo, en el nivel de documento o mensaje de correo electrónico que los usuarios finales pueden aplicar manualmente además de la aplicación automática por parte de los administradores. También puede aplicar una etiqueta de retención a una biblioteca de documentos, carpeta o conjunto de documentos en SharePoint, de modo que todos los documentos almacenados en esa ubicación hereden la etiqueta de retención predeterminada.

Además, las etiquetas de retención admiten [la administración](records-management.md) de registros para marcar el contenido como un registro. Cuando esto sucede, la etiqueta coloca restricciones adicionales en el contenido que podrían ser necesarias para ayudar a su organización a cumplir con los requisitos normativos.

Para obtener instrucciones paso a paso para crear y publicar etiquetas de retención, consulte la siguiente guía:
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

Para empezar con la administración de registros, vea [Introducción a la administración de registros](get-started-with-records-management.md).

### <a name="identify-and-define-sensitive-information-types"></a>Identificar y definir tipos de información confidencial

Defina tipos de información confidencial en función del patrón contenido en la información de los datos de su organización. Usar [tipos de información confidencial](./sensitive-information-type-entity-definitions.md) integrados ayuda a identificar y proteger números de tarjetas de crédito, números de cuenta bancaria, números de pasaporte y mucho más. O cree sus [propios tipos de información de confidencialidad personalizados](create-a-custom-sensitive-information-type.md) específicos de su organización.

Para obtener instrucciones paso a paso para definir tipos de información confidencial personalizados, vea [Create a custom sensitive information type in the Security & Compliance Center](./create-a-custom-sensitive-information-type.md).

### <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

[Las directivas de prevención](data-loss-prevention-policies.md) de pérdida de datos (DLP) permiten identificar, supervisar y proteger automáticamente la información confidencial en toda la organización de Microsoft 365. Use directivas DLP para identificar elementos confidenciales en los servicios Microsoft, evitar el uso compartido accidental de elementos confidenciales y ayudar a los usuarios a aprender a cumplir sin interrumpir su flujo de trabajo.

Para obtener instrucciones paso a paso para configurar directivas DLP, [cree, pruebe y ajuste una directiva DLP.](create-test-tune-dlp-policy.md) Para obtener información sobre licencias de administración de pérdida de datos, vea Instrucciones de licencias de [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)para seguridad & cumplimiento .

### <a name="detect-and-act-on-insider-risks"></a>Detectar y actuar en riesgos de insider

Cada vez más, los empleados tienen cada vez más acceso a crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, al tiempo que cumplen los requisitos de cumplimiento y los estándares de privacidad de los empleados. Estos riesgos pueden incluir el robo de datos al salir de los empleados y las pérdidas de datos de información fuera de la organización por sobresharing accidental o intenciones malintencionadas.

La administración de riesgos de [Insider](insider-risk-management-policies.md) en Microsoft 365 usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, recortar y actuar rápidamente en la actividad de usuario de riesgo. Al usar registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de insider permite definir directivas específicas para identificar indicadores de riesgo y tomar medidas para mitigar estos riesgos.

Para obtener instrucciones paso a paso para planear y configurar directivas de administración de riesgos internas, vea [Plan for insider risk management](insider-risk-management-plan.md) y Get started with [insider risk management](insider-risk-management-configure.md). Para obtener información sobre licencias de administración de riesgos insider, consulte Guía de licencias de [Microsoft 365 para](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)seguridad & cumplimiento .