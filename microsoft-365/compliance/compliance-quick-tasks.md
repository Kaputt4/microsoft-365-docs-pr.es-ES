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
description: Obtenga información sobre las tareas que le ayudarán a empezar rápidamente con el cumplimiento normativo en Microsoft 365.
ms.openlocfilehash: 36b6e2bd0d0339241748499826edf061a7259317
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928634"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Tareas rápidas para empezar a usar el Centro de cumplimiento de Microsoft 365

Si no está al tanto del cumplimiento de Microsoft 365 y se pregunta por dónde empezar, en este artículo se proporcionan instrucciones sobre los conceptos básicos y se da prioridad a las tareas de cumplimiento importantes. Este artículo le ayudará a empezar rápidamente a administrar y supervisar los datos, proteger la información y minimizar los riesgos de insider.

Este artículo también es útil si está averiguando la mejor manera de administrar los riesgos, proteger los datos y cumplir con las normativas y estándares con un nuevo personal remoto. Los empleados ahora colaboran y se conectan entre sí de nuevas maneras, lo que significa que es posible que los controles y procesos de cumplimiento existentes deban adaptarse. Identificar y administrar estos nuevos riesgos de cumplimiento dentro de la organización es fundamental para proteger los datos y minimizar las amenazas y riesgos.

Después de completar estas tareas básicas de cumplimiento, considere la posibilidad de ampliar la cobertura de cumplimiento en su organización mediante la implementación de soluciones de cumplimiento de Microsoft 365 adicionales.

## <a name="task-1-configure-compliance-permissions"></a>Tarea 1: Configurar permisos de cumplimiento

Es importante administrar quién de su organización tiene acceso al Centro de cumplimiento de Microsoft 365 para ver contenido y realizar tareas de administración. Microsoft 365 proporciona roles administrativos específicos para el cumplimiento y para usar las herramientas incluidas en el Centro de cumplimiento de Microsoft 365.

Empiece asignando permisos de cumplimiento a las personas de su organización para que puedan realizar estas tareas e impedir que personas no autorizadas tengan acceso a áreas fuera de sus responsabilidades. Antes de empezar a configurar e implementar soluciones de  cumplimiento incluidas  con Microsoft 365, debe asegurarse de que ha asignado las personas adecuadas al administrador de datos de cumplimiento y a los roles de administrador de cumplimiento. También tendrá que asignar usuarios al rol de lector global de Azure Active Directory para ver datos en el Administrador de cumplimiento.

Para obtener instrucciones paso a paso para configurar permisos y asignar personas a roles de administrador, consulte Permisos en el Centro de [seguridad & cumplimiento.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

## <a name="task-2-know-your-state-of-compliance"></a>Tarea 2: Conocer su estado de cumplimiento

Es difícil saber dónde ir si no sabe dónde está. Satisfacer sus necesidades de cumplimiento incluye comprender su nivel actual de riesgo y qué actualizaciones pueden ser necesarias en estos momentos cambiantes. Tanto si su organización es nueva en los requisitos de cumplimiento normativo como si tiene una amplia experiencia con los estándares y normativas que rigen su sector, lo mejor que puede hacer para mejorar el cumplimiento es comprender dónde se encuentra su organización.

[El Administrador de cumplimiento de Microsoft](compliance-manager.md) puede ayudarle a comprender la posición de cumplimiento de su organización y resaltar las áreas que pueden necesitar mejoras. El Administrador de cumplimiento usa un panel centralizado para calcular una puntuación basada en riesgos, midiendo su progreso en la realización de acciones que ayudan a reducir los riesgos en torno a la protección de datos y los estándares normativos. También puede usar el Administrador de cumplimiento como herramienta para realizar un seguimiento de todas las evaluaciones de riesgos. Proporciona capacidades de flujo de trabajo para ayudarle a completar eficazmente las evaluaciones de riesgos a través de una herramienta común.

Para obtener instrucciones paso a paso para empezar a trabajar con el Administrador de cumplimiento, consulte Introducción al Administrador [de cumplimiento.](compliance-manager-setup.md)

>[!IMPORTANT]
>La seguridad y el cumplimiento están estrechamente integrados para la mayoría de las organizaciones. Es importante que su organización aborde las áreas básicas de seguridad, protección contra amenazas y administración de identidades y acceso para ayudar a proporcionar un enfoque de defensa en profundidad para la seguridad y el cumplimiento.
>
>Compruebe la puntuación de seguridad de [Microsoft 365](../security/mtp/microsoft-secure-score.md) en el Centro de seguridad de Microsoft 365 y complete las tareas descritas en los siguientes artículos:
>
> - [Mapa de ruta de seguridad: principales prioridades para los primeros 30 días, 90 días y posteriores](../security/office-365-security/security-roadmap.md)
> - [Las 12 tareas principales para que los equipos de seguridad admitan el trabajo desde casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarea 3: Habilitar la auditoría para su organización

Ahora que ha determinado el estado actual de su organización y quién puede administrar las funciones de cumplimiento, el siguiente paso es asegurarse de que tiene los datos para llevar a cabo investigaciones de cumplimiento y generar informes para las actividades de red y de usuario en su organización. Habilitar la auditoría también es un requisito previo importante para las soluciones de cumplimiento que se tratan más adelante en este artículo.

Las conclusiones proporcionadas por el registro de auditoría son una herramienta valiosa para ayudar a cumplir los requisitos de cumplimiento con soluciones que pueden ayudarle a administrar y supervisar las áreas de cumplimiento que necesitan mejora. El registro de auditoría debe estar habilitado antes de que se registren las actividades y antes de poder buscar en el registro de auditoría. Cuando se habilita, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se conserva durante 90 días y hasta un año, según la licencia asignada a los usuarios.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del registro [de auditoría.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarea 4: Crear directivas para alertar sobre posibles problemas de cumplimiento

Microsoft proporciona varias directivas de alerta integradas que ayudan a identificar el abuso de permisos de administrador, la actividad de malware, las posibles amenazas internas y externas, y los riesgos de gobierno de la información. Estas directivas están activadas de forma predeterminada, pero es posible que deba configurar alertas personalizadas para ayudar a administrar los requisitos de cumplimiento específicos de su organización.

Usa la directiva de alerta y las herramientas del panel de alertas para crear directivas de alerta personalizadas y ver las alertas generadas cuando los usuarios realizan actividades que coinciden con las condiciones de la directiva. Algunos ejemplos pueden ser usar directivas de alerta para realizar un seguimiento de las actividades de usuario y administrador que afectan a los requisitos de cumplimiento, permisos e incidentes de pérdida de datos en su organización.

Para obtener instrucciones paso a paso para crear directivas de alerta personalizadas, consulte Directivas de alerta en el Centro de seguridad [y cumplimiento.](alert-policies.md)

## <a name="task-5-classify-and-protect-sensitive-data"></a>Tarea 5: Clasificar y proteger datos confidenciales

Para realizar su trabajo, las personas de su organización colaboran con otras tanto dentro como fuera de la organización. Esto significa que el contenido ya no se queda detrás de un firewall, sino que puede desplazarse a todas partes, a través de dispositivos, aplicaciones y servicios. Y cuando se desplaza, usted quiere que lo haga de una forma segura y protegida que cumpla con las directivas empresariales y de cumplimiento de normas de su organización.

[Las etiquetas](sensitivity-labels.md) de confidencialidad le permiten clasificar y proteger los datos de su organización, a la vez que se asegura de que la productividad de los usuarios y su capacidad de colaboración no se ve obstaculizada. Use etiquetas de confidencialidad para aplicar el cifrado y las restricciones de uso aplican marcas visuales y protegen la información en plataformas y dispositivos, locales y en la nube.

Para obtener instrucciones paso a paso para configurar y usar etiquetas de confidencialidad, vea Introducción a [las etiquetas de confidencialidad.](get-started-with-sensitivity-labels.md) Para obtener información sobre las licencias de etiquetas de confidencialidad, consulte las instrucciones de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)para la seguridad & cumplimiento.

## <a name="task-6-configure-a-retention-policy"></a>Tarea 6: Configurar una directiva de retención

Una [directiva de](retention.md) retención le permite decidir de forma proactiva si desea retener contenido, eliminar contenido o ambos: retener y, a continuación, eliminar el contenido al final de un período de retención especificado. Estas acciones pueden ser necesarias para cumplir con las normativas del sector y las directivas internas, así como reducir el riesgo en caso de litigio o una infracción de seguridad.

Cuando el contenido está sujeto a una directiva de retención, los usuarios pueden seguir editando y trabajando con el contenido como si nada hubiera cambiado. El contenido se conserva en su ubicación original. Pero si alguien edita o elimina contenido que está sujeto a la directiva de retención, se guarda una copia del contenido original en una ubicación segura donde se conserva mientras la directiva de retención para ese contenido está en vigor.

Puede establecer rápidamente una directiva de retención para varias ubicaciones en su entorno de Microsoft 365, como correo de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365. No hay límites en el número de buzones o sitios que esta directiva puede incluir automáticamente. Pero si necesita ser más selectivo, puede hacerlo configurando una directiva de retención para ubicaciones específicas e incluir o excluir sitios o usuarios.

Para obtener instrucciones paso a paso para configurar una directiva de retención, vea [Crear y configurar directivas de retención.](create-retention-policies.md) Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a las directivas y etiquetas de retención](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Tarea 7: Configurar la información confidencial y las directivas de lenguaje ofensivo

Proteger la información confidencial y detectar y actuar en incidentes de acoso en el lugar de trabajo es una parte importante del cumplimiento de las directivas y estándares internos. [El cumplimiento de](communication-compliance-feature-reference.md) las comunicaciones en Microsoft 365 ayuda a minimizar estos riesgos al ayudarle a detectar, capturar y tomar rápidamente medidas correctivas para el correo electrónico y las comunicaciones de Microsoft Teams. Estas incluyen comunicaciones inadecuadas que contienen blasfedad, amenazas, acoso y comunicaciones que comparten información confidencial dentro y fuera de su organización.

Un lenguaje ofensivo  predefinido y una plantilla de directiva contra acoso le permite examinar las comunicaciones internas y externas en busca de coincidencias de directivas para que los revisores designados puedan examinarla. Los revisores pueden investigar el correo electrónico examinado, Microsoft Teams, Yammer o las comunicaciones de terceros en su organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen con los estándares de su organización.

La plantilla de  directiva de información confidencial predefinida le ayuda a crear rápidamente una directiva para examinar el correo electrónico y las comunicaciones de Microsoft Teams que contienen palabras clave o tipos de información confidencial definidos para asegurarse de que los datos importantes no se comparten con personas que no deberían tener acceso. Estas actividades pueden incluir comunicaciones no autorizadas sobre proyectos confidenciales o reglas específicas del sector sobre el comercio interno u otras actividades de colusión.

Para obtener instrucciones paso a paso para planear y configurar el cumplimiento de comunicaciones, vea [Plan for communication compliance](communication-compliance-plan.md) y Get started with communication [compliance](communication-compliance-configure.md). Para obtener información sobre las licencias de cumplimiento de comunicaciones, vea las instrucciones de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)para la seguridad & cumplimiento.

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Tarea 8: Ver lo que ocurre con los elementos confidenciales

Las etiquetas de confidencialidad, los tipos de información confidencial, las etiquetas y directivas de retención y los clasificadores que se pueden entrenar se pueden usar para clasificar y etiquetar elementos confidenciales en Exchange, SharePoint y OneDrive, como ha visto en las tareas anteriores. El último paso de su recorrido de tareas rápido es ver qué elementos se etiquetaron y qué acciones están llevando a cabo los usuarios en esos elementos confidenciales. [el explorador de contenido](data-classification-content-explorer.md) [y el explorador de actividades](data-classification-activity-explorer.md) proporcionan esta visibilidad.

### <a name="content-explorer"></a>Explorador de contenido
 El explorador de contenido le permite ver, en su formato nativo, todos los elementos que se han clasificado como un tipo de información confidencial o que pertenecen a una clasificación determinada por un clasificador que se puede entrenar, así como todos los elementos que tienen aplicada la etiqueta de confidencialidad o retención.

Para obtener instrucciones paso a paso para [](data-classification-overview.md)usar el explorador de contenido, vea Información general sobre la clasificación de datos y Introducción al explorador [de contenido.](data-classification-content-explorer.md)

### <a name="activity-explorer"></a>Explorador de actividades
El explorador de actividades te ayuda a supervisar lo que se está haciendo con los elementos confidenciales clasificados y etiquetados en:
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

Para obtener instrucciones paso a paso para usar el explorador de actividades, vea [Introducción al explorador de actividades.](data-classification-activity-explorer.md)

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha configurado los conceptos básicos para la administración de cumplimiento para su organización, tenga en cuenta las siguientes soluciones de cumplimiento en Microsoft 365 para ayudarle a proteger la información confidencial y detectar y actuar sobre riesgos adicionales de insider.

### <a name="configure-retention-labels"></a>Configurar etiquetas de retención

Aunque las directivas de retención se aplican en el nivel de contenedor a ubicaciones como sitios de SharePoint y buzones de [Exchange,](retention.md#retention-labels) las etiquetas de retención permiten una orientación más específica para las directivas de retención y eliminación. Por ejemplo, en el nivel de mensaje de correo electrónico o documento que los usuarios finales pueden aplicar manualmente además de la aplicación automática por parte de los administradores. También puede aplicar una etiqueta de retención a una biblioteca de documentos, carpeta o conjunto de documentos en SharePoint, de modo que todos los documentos almacenados en esa ubicación hereden la etiqueta de retención predeterminada.

Además, las etiquetas de retención [admiten la administración de](records-management.md) registros para marcar el contenido como un registro. Cuando esto sucede, la etiqueta coloca restricciones adicionales en el contenido que pueden ser necesarios para ayudar a su organización a cumplir con los requisitos normativos.

Para obtener instrucciones paso a paso para crear y publicar etiquetas de retención, vea las siguientes instrucciones:
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

Para empezar a usar la administración de registros, vea [Introducción a la administración de registros.](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Identificar y definir tipos de información confidencial

Defina tipos de información confidencial en función del patrón contenido en la información de los datos de su organización. Usar [tipos de información confidencial](what-the-sensitive-information-types-look-for.md) integrados ayuda a identificar y proteger números de tarjeta de crédito, números de cuentas bancarias, números de pasaporte y mucho más. O cree sus [propios tipos de información de confidencialidad personalizados](create-a-custom-sensitive-information-type.md) específicos para su organización.

Para obtener instrucciones paso a paso para definir tipos personalizados de información confidencial, vea Crear un tipo personalizado de información confidencial en el Centro de [seguridad & cumplimiento.](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)

### <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

[Las directivas de prevención](data-loss-prevention-policies.md) de pérdida de datos (DLP) permiten identificar, supervisar y proteger automáticamente información confidencial en toda la organización de Microsoft 365. Use directivas DLP para identificar elementos confidenciales en los servicios Microsoft, evitar el uso compartido accidental de elementos confidenciales y ayudar a los usuarios a aprender a cumplir las normas sin interrumpir su flujo de trabajo.

Para obtener instrucciones paso a paso para configurar directivas DLP, [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md). Para obtener información sobre las licencias de administración de pérdida de datos, vea las instrucciones de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)para la seguridad & cumplimiento.

### <a name="detect-and-act-on-insider-risks"></a>Detectar y actuar en riesgos de insider

Cada vez más, los empleados tienen cada vez más acceso para crear, administrar y compartir datos en una amplia variedad de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, a la vez que cumplen los requisitos de cumplimiento y los estándares de privacidad de los empleados. Estos riesgos pueden incluir el robo de datos al salir de los empleados y la pérdida de información fuera de la organización por uso compartido accidental o intenciones malintencionadas.

La administración de riesgos de [Insider](insider-risk-management-policies.md) en Microsoft 365 usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, recortar y actuar rápidamente en actividades de usuario de riesgo. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de Insider le permite definir directivas específicas para identificar indicadores de riesgo y tomar medidas para mitigar estos riesgos.

Para obtener instrucciones paso a paso para planear y configurar directivas de administración de riesgos internas, vea [Plan for insider risk management](insider-risk-management-plan.md) and Get started with [insider risk management](insider-risk-management-configure.md). Para obtener información acerca de las licencias de administración de riesgos de Insider, consulte la guía de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)para la seguridad & cumplimiento.
