---
title: Información sobre riesgos internos de Microsoft
description: Obtenga información sobre cómo ayudar a minimizar el riesgo en su organización con la administración de riesgos internos en Microsoft Purview.
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- highpri
- tier1
- purview-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- highpri
ms.openlocfilehash: 65ec1b52582b1cbefb9a4b995118bb7f60d0081d
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793332"
---
# <a name="learn-about-insider-risk-management"></a>Información sobre riesgos internos de Microsoft

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

La Administración de riesgos internos de Microsoft Purview es una solución de cumplimiento que ayuda a minimizar los riesgos internos, ya que le permite detectar, investigar y actuar en actividades malintencionadas e involuntarias en su organización. Las directivas de riesgos internos le permiten definir los tipos de riesgos a identificar y detectar en su organización, incluida la acción sobre casos y la elevación de casos a Microsoft eDiscovery (Premium) si es necesario. Los analistas de riesgo de su organización pueden tomar rápidamente las medidas adecuadas para asegurarse de que los usuarios cumplen los estándares de cumplimiento de su organización.

Para obtener más información y información general sobre el proceso de planeamiento para abordar actividades potencialmente de riesgo en su organización que pueden provocar un incidente de seguridad, consulte [Inicio de un programa de administración de riesgos internos](https://download.microsoft.com/download/b/2/0/b208282a-2482-4986-ba07-15a9b9286df0/pwc-starting-an-insider-risk-management-program-with-pwc-and-microsoft.pdf).

Vea los vídeos siguientes para obtener información sobre cómo la administración de riesgos internos puede ayudar a su organización a prevenir, detectar y contener riesgos a la vez que prioriza los valores, la cultura y la experiencia del usuario de la organización:

**Solución de administración de riesgos internos & desarrollo**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

**Flujo de trabajo de administración de riesgos internos**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

Consulte el [vídeo de Microsoft Mechanics](https://www.youtube.com/watch?v=Ynkfu8OF0wQ) sobre cómo funcionan conjuntamente la administración de riesgos internos y el cumplimiento de comunicaciones para ayudar a minimizar los riesgos de datos de los usuarios de su organización.

> [!IMPORTANT]
> La administración de riesgos internos está disponible actualmente en inquilinos hospedados en regiones geográficas y países compatibles con las dependencias del servicio de Azure. Para comprobar que la administración de riesgos internos es compatible con su organización, consulte [Disponibilidad de dependencias de Azure por país o región](/troubleshoot/azure/general/dependency-availability-by-country).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="modern-risk-pain-points"></a>Puntos de dolor de riesgo modernos

La administración y minimización de los riesgos en su organización empieza con la comprensión de los tipos de riesgos que se encuentran en Modern Workplace. Algunos riesgos están controlados por eventos externos y factores que están fuera del control directo. Otros riesgos se deben a eventos internos y acciones de usuario que se pueden minimizar y evitar. Algunos ejemplos son los riesgos de comportamientos y acciones ilegales, inadecuados, no autorizados o no éticos por parte de los usuarios de la organización. Estos comportamientos incluyen una amplia gama de riesgos internos de los usuarios:

- Filtraciones de datos confidenciales y pérdida de datos
- Infracciones de confidencialidad
- Robo de propiedad intelectual
- Fraude
- Tráfico de información privilegiada
- Infracciones de cumplimiento normativo

Los usuarios del área de trabajo moderna tienen acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, a la vez que cumplen los estándares de privacidad de los usuarios.

La administración de riesgos internos usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar y actuar rápidamente sobre la actividad de riesgo. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo. Estas directivas le permiten identificar actividades de riesgo y actuar para mitigar estos riesgos.

La administración de riesgos internos se centra en los siguientes principios:

- **Transparencia**: equilibre la privacidad del usuario frente al riesgo de la organización con la arquitectura de privacidad por diseño.
- **Configurable**: directivas configurables basadas en el sector, geográficas y grupos empresariales.
- **Integrado**: flujo de trabajo integrado en las soluciones de Microsoft Purview.
- **Accionable**: proporciona información para habilitar las notificaciones del revisor, las investigaciones de datos y las investigaciones de usuario.

## <a name="identifying-potential-risks-with-analytics"></a>Identificación de posibles riesgos con análisis

Los análisis de riesgos internos le permiten realizar una evaluación de los posibles riesgos internos en su organización sin necesidad de configurar ninguna directiva de riesgos internos. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar. Esta evaluación también puede ayudarle a determinar las necesidades de licencias adicionales o la optimización futura de las directivas de riesgo internos existentes.

Para más información sobre el análisis de riesgos internos, consulte [Configuración de administración de riesgos internos: Análisis](insider-risk-management-settings.md#analytics).

## <a name="get-started-with-recommended-actions-preview"></a>Introducción a las acciones recomendadas (versión preliminar)

Tanto si va a configurar la administración de riesgos internos por primera vez como si está empezando a crear nuevas directivas, la nueva experiencia [de acciones recomendadas](insider-risk-management-configure.md#recommended-actions-preview) puede ayudarle a sacar el máximo partido a las funcionalidades de administración de riesgos internos. Entre las acciones recomendadas se incluyen la configuración de permisos, la elección de indicadores de directiva, la creación de una directiva, etc.

## <a name="workflow"></a>Flujo de trabajo

El flujo de trabajo de administración de riesgos internos le ayuda a identificar, investigar y tomar medidas para abordar los riesgos internos en su organización. Con plantillas de directivas centradas, señalización de actividad completa en el servicio Microsoft 365 y herramientas de administración de alertas y casos, puede usar información procesable para identificar y actuar rápidamente sobre comportamientos de riesgo.

La identificación y resolución de actividades de riesgo internas y problemas de cumplimiento con la administración de riesgos internos usa el flujo de trabajo siguiente:

![Flujo de trabajo de administración de riesgos internos.](../media/insider-risk-workflow.png)

### <a name="policies"></a>Directivas

[Las directivas de administración de riesgos](insider-risk-management-policies.md) internos se crean mediante plantillas predefinidas y condiciones de directiva que definen qué eventos desencadenantes e indicadores de riesgo se examinan en su organización. Estas condiciones incluyen cómo se usan los indicadores de riesgo para las alertas, qué usuarios se incluyen en la directiva, qué servicios se priorizan y el período de tiempo de detección.

Puede seleccionar entre las siguientes plantillas de directiva para empezar a trabajar rápidamente con la administración de riesgos internos:

- [Robo de datos por parte de los usuarios que abandonan la organización](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Filtración de datos](insider-risk-management-policies.md#data-leaks)
- [Filtración de datos por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Pérdidas de datos por parte de usuarios de riesgo (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-risky-users-preview)
- [Infracciones de directivas de seguridad (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-preview)
- [Uso indebido de datos del paciente (versión preliminar)](insider-risk-management-policies.md#patient-data-misuse-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios de riesgo (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-risky-users-preview)

![Panel de directivas de administración de riesgos internos.](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Las alertas se generan automáticamente mediante indicadores de riesgo que coinciden con las condiciones de la directiva y se muestran en el [panel Alertas](insider-risk-management-activities.md#alert-dashboard). Este panel ofrece una vista rápida de todas las alertas que se deben revisar, alertas abiertas a lo largo del tiempo y estadísticas de alertas de la organización. Todas las alertas de directiva se muestran con la siguiente información para ayudarle a identificar rápidamente el estado de las alertas existentes y las nuevas alertas que necesitan acción:

- Estado
- Severity
- Tiempo detectado
- Case
- Estado del caso

![Panel de alertas de administración de riesgos internos.](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Clasificación

Las nuevas actividades de usuario que necesitan investigación generan automáticamente alertas a las que se les asigna un estado *de revisión Necesidades* . Los revisores pueden identificar y revisar rápidamente, evaluar y evaluar estas alertas.

Para resolver las alertas, se abre un nuevo caso, se asigna la alerta a un caso existente o se descarta la alerta. Con los filtros de alertas, es fácil identificar rápidamente las alertas por estado, gravedad o tiempo detectado. Como parte del proceso de evaluación de prioridades, los revisores pueden ver los detalles de las alertas de las actividades identificadas por la directiva, ver la actividad del usuario asociada a la coincidencia de directiva, ver la gravedad de la alerta y revisar la información del perfil de usuario.

![Evaluación interna de la administración de riesgos.](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigación

Investigue rápidamente todas las actividades de riesgo de un usuario seleccionado con [informes de actividad de usuario (versión preliminar).](insider-risk-management-activities.md#user-activity-reports) Estos informes permiten a los investigadores de su organización examinar las actividades de usuarios específicos durante un período de tiempo definido sin tener que asignarlas de forma temporal o explícita a una directiva de administración de riesgos internos. Después de examinar las actividades de un usuario, los investigadores pueden descartar actividades individuales como benignas, compartir o enviar por correo electrónico un vínculo al informe con otros investigadores, o elegir asignar al usuario temporal o explícitamente a una directiva de administración de riesgos internos.

[Los casos](insider-risk-management-cases.md) se crean para las alertas que requieren una revisión e investigación más detalladas de los detalles y las circunstancias de la actividad en torno a la coincidencia de directivas. El **panel de casos** ofrece una vista integral de todos los casos activos, casos abiertos a lo largo del tiempo y estadísticas de casos para la organización. Los revisores pueden filtrar rápidamente los casos por estado, la fecha en que se abrió el caso y la fecha en que se actualizó el caso por última vez.

Si se selecciona un caso en el panel de casos, se abre el caso para su investigación y revisión. Este paso es el núcleo del flujo de trabajo de administración de riesgos internos. Esta área es donde las actividades de riesgo, las condiciones de directiva, los detalles de alertas y los detalles del usuario se sintetizan en una vista integrada para los revisores. Las herramientas de investigación principales de esta área son:

- **Actividad del usuario**: la actividad de riesgo del usuario se muestra automáticamente en un gráfico interactivo que traza las actividades a lo largo del tiempo y por nivel de riesgo para las actividades de riesgo actuales o pasadas. Los revisores pueden filtrar y ver rápidamente todo el historial de riesgos del usuario y profundizar en actividades específicas para obtener más detalles.
- **Explorador de contenido**: todos los archivos de datos y mensajes de correo electrónico asociados a las actividades de alerta se capturan y muestran automáticamente en el Explorador de contenido. Los revisores pueden filtrar y ver archivos y mensajes por origen de datos, tipo de archivo, etiquetas, conversación y muchos más atributos.
- **Notas del caso**: los revisores pueden proporcionar notas para un caso en la sección Notas del caso. Esta lista consolida todas las notas en una vista central e incluye información de revisor y fecha enviada.

![Investigación de administración de riesgos internos.](../media/insider-risk-investigate.png)

Además, el nuevo [registro de auditoría (versión preliminar)](insider-risk-management-audit-log.md) le permite mantenerse informado de las acciones que se realizaron en las características de administración de riesgos internos. Este recurso permite una revisión independiente de las acciones realizadas por los usuarios asignados a uno o varios grupos de roles de administración de riesgos internos.

### <a name="action"></a>Acción

Una vez investigados los casos, los revisores pueden actuar rápidamente para resolver el caso o colaborar con otras partes interesadas de riesgo de la organización. Si los usuarios infringen accidental o involuntariamente las condiciones de la directiva, se puede enviar al usuario un aviso sencillo desde las plantillas de aviso que puede personalizar para su organización. Estos avisos pueden servir como recordatorios simples o pueden dirigir al usuario a un entrenamiento de actualización o una guía para ayudar a evitar comportamientos de riesgo futuros. Para más información, consulte [plantillas de notificación de administración de riesgos internos](insider-risk-management-notices.md).

En situaciones más graves, es posible que tenga que compartir la información del caso de administración de riesgos internos con otros revisores o servicios de su organización. La administración de riesgos internos está estrechamente integrada con otras soluciones de Microsoft Purview para ayudarle con la resolución de riesgos de un extremo a otro.

- **eDiscovery (Premium):** escalar un caso para investigación le permite transferir datos y administración del caso a Microsoft Purview eDiscovery (Premium). eDiscovery (Premium) ofrece un flujo de trabajo de un extremo a otro para conservar, recopilar, revisar, analizar y exportar el contenido que responde a las investigaciones internas y externas de la organización. Permite que los equipos legales administren todo el flujo de trabajo de notificaciones de suspensión legal. Para obtener más información sobre los casos de eDiscovery (Premium), consulte [Información general de Microsoft Purview eDiscovery (Premium).](overview-ediscovery-20.md)
- **Integración de las API de administración de Office 365 (versión preliminar):** la administración de riesgos internos admite la exportación de información de alertas a servicios de administración de eventos e información de seguridad (SIEM) a través de las API de administración de Office 365. Tener acceso a la información de alertas en la plataforma que mejor se adapte a los procesos de riesgo de su organización le proporciona más flexibilidad para actuar sobre las actividades de riesgo. Para más información sobre la exportación de información de alertas con las API de administración de Office 365, consulte [Exportación de alertas](insider-risk-management-settings.md#export-alerts).

> [!NOTE]
> Gracias por sus comentarios y soporte técnico durante la versión preliminar del conector de ServiceNow. Hemos decidido finalizar la versión preliminar del conector de ServiceNow y dejar de admitir la administración de riesgos internos el 30 de noviembre de 2020. Estamos evaluando activamente métodos alternativos para proporcionar a los clientes la integración de ServiceNow en la administración de riesgos internos.

## <a name="scenarios"></a>Escenarios

La administración de riesgos internos puede ayudarle a detectar, investigar y tomar medidas para mitigar los riesgos internos en su organización en varios escenarios comunes:

### <a name="data-theft-by-departing-users"></a>Robo de datos por parte de los usuarios que abandonan la organización

Cuando los usuarios abandonan una organización, ya sea voluntariamente o como resultado de la terminación, a menudo hay preocupaciones legítimas de que la empresa, el cliente y los datos de usuario están en riesgo. Los usuarios pueden suponer inocentemente que los datos del proyecto no son propiedad de la empresa, o pueden verse tentados a tomar datos de la empresa para obtener ganancias personales e infringir la política de la empresa y los estándares legales. Las directivas de administración de riesgos internos que usan la plantilla de directiva [Robo de datos al salir de los usuarios](insider-risk-management-policies.md#policy-templates) detectan automáticamente actividades asociadas normalmente con este tipo de robo. Con esta directiva, recibirá automáticamente alertas de actividades sospechosas asociadas con el robo de datos por parte de los usuarios que abandonan el servicio para que pueda realizar las acciones de investigación adecuadas. La configuración de un [conector de RR. HH. de Microsoft 365](import-hr-data.md) para su organización es necesaria para esta plantilla de directiva.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Fuga intencionada o involuntaria de información confidencial o confidencial

En la mayoría de los casos, los usuarios hacen todo lo posible para controlar correctamente la información confidencial o confidencial. Pero en ocasiones, los usuarios pueden cometer errores y la información se comparte accidentalmente fuera de su organización o infringe las directivas de protección de la información. En otras circunstancias, los usuarios pueden filtrar o compartir intencionadamente información confidencial con intenciones malintencionadas y para posibles ganancias personales. Las directivas de administración de riesgos internos creadas con las siguientes plantillas de directiva de pérdida de datos detectan automáticamente actividades asociadas normalmente con el uso compartido de información confidencial o confidencial:

- [Filtración de datos](insider-risk-management-policies.md#data-leaks)
- [Filtración de datos por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Pérdidas de datos por parte de usuarios de riesgo (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-risky-users-preview)

### <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Infracciones de directivas de seguridad intencionadas o involuntarias (versión preliminar)

Los usuarios suelen tener un gran grado de control al administrar sus dispositivos en el área de trabajo moderna. Este control puede incluir permisos para instalar o desinstalar las aplicaciones necesarias en el desempeño de sus tareas o la capacidad de deshabilitar temporalmente las características de seguridad del dispositivo. Independientemente de si esta actividad de riesgo es involuntaria, accidental o malintencionada, esta conducta puede suponer un riesgo para su organización y es importante identificar y actuar para minimizar. Para ayudar a identificar estas actividades de seguridad de riesgo, las siguientes plantillas de infracción de directivas de seguridad de administración de riesgos internos puntúan los indicadores de riesgo de seguridad y usan alertas de Microsoft Defender para punto de conexión para proporcionar información sobre las actividades relacionadas con la seguridad:

- [Infracciones de directivas de seguridad (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios de riesgo (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-risky-users-preview)

### <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Directivas para usuarios basadas en la posición, el nivel de acceso o el historial de riesgos (versión preliminar)

Los usuarios de su organización pueden tener distintos niveles de riesgo en función de su posición, nivel de acceso a información confidencial o historial de riesgos. Esta estructura puede incluir miembros del equipo directivo ejecutivo de la organización, administradores de TI que tienen amplios privilegios de acceso a datos y redes o usuarios con un historial pasado de actividades de riesgo. En estas circunstancias, una inspección más cercana y una puntuación de riesgo más agresiva son importantes para ayudar a exponer alertas para la investigación y la acción rápida. Para ayudar a identificar actividades de riesgo para estos tipos de usuarios, puede crear grupos de usuarios prioritarios y crear directivas a partir de las siguientes plantillas de directiva:

- [Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Filtración de datos por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

### <a name="healthcare-preview"></a>Healthcare (versión preliminar)

En el caso de las organizaciones de la industria sanitaria, estudios recientes han encontrado una tasa muy alta de infracciones de datos relacionadas con los usuarios internos. La detección del uso indebido de los datos de los pacientes y la información de los registros de salud es un componente fundamental para proteger la privacidad de los pacientes y cumplir con la normativa de cumplimiento, como la Ley de Portabilidad y Responsabilidad del Seguro De Salud (HIPAA) y la Ley de Tecnología de información sanitaria para la salud económica y clínica (HITECH). El uso indebido de los datos de los pacientes puede ir desde el acceso a registros de pacientes con privilegios hasta el acceso a registros de pacientes de familiares o vecinos con intenciones malintencionadas. Para ayudar a identificar estos tipos de actividades de riesgo, las siguientes plantillas de directivas de administración de riesgos internos usan el conector de RR. HH. de Microsoft 365 y un conector de datos específico para la salud para empezar a puntuar indicadores de riesgo relacionados con comportamientos que pueden producirse en los sistemas de registro de salud electrónico (EHR):

- [Uso indebido de datos del paciente (versión preliminar)](insider-risk-management-policies.md#patient-data-misuse-preview)

### <a name="actions-and-behaviors-by-risky-users-preview"></a>Acciones y comportamientos de usuarios de riesgo (versión preliminar)

Los eventos de estrés laboral pueden afectar al comportamiento del usuario de varias maneras relacionadas con los riesgos internos. Estos factores de estrés pueden ser una revisión de rendimiento deficiente, una disminución de posición o la colocación del usuario en un plan de revisión de rendimiento. Los factores de estrés también pueden dar lugar a un comportamiento potencialmente inadecuado, como el envío de usuarios potencialmente amenazantes, hostigamiento o lenguaje discriminatorio en el correo electrónico y otros mensajes. Aunque la mayoría de los usuarios no responden malintencionadamente a estos eventos, el estrés de estas acciones puede dar lugar a que algunos usuarios se comporten de maneras que normalmente no consideren en circunstancias normales. Para ayudar a identificar estos tipos de actividades potencialmente arriesgadas, las siguientes plantillas de directivas de administración de riesgos internos pueden usar el conector de RR. HH. o la integración con una [directiva de cumplimiento de comunicaciones dedicada](/microsoft-365/compliance/communication-compliance-policies#integration-with-insider-risk-management-preview) para que los usuarios entren en el ámbito de las directivas de administración de riesgos internos y empiecen a puntuar los indicadores de riesgo relacionados con los comportamientos que pueden producirse:

- [Pérdidas de datos por parte de usuarios de riesgo (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-risky-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios de riesgo (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-risky-users-preview)

### <a name="visual-context-for-potentially-risky-user-activities-with-forensic-evidence-preview"></a>Contexto visual para actividades de usuario potencialmente arriesgadas con pruebas forenses (versión preliminar)

Tener contexto visual es fundamental para que los equipos de seguridad durante las investigaciones forenses obtengan mejor información sobre las actividades de usuario potencialmente arriesgadas que pueden provocar un incidente de seguridad. Esto puede incluir la captura visual de estas actividades para ayudar a evaluar si son realmente arriesgadas o sacadas de contexto y no potencialmente arriesgadas. Para las actividades que se determinan como de riesgo, tener capturas de pruebas forenses puede ayudar a los investigadores y a su organización a mitigar, comprender y responder mejor a estas actividades. Para ayudar con este escenario, [habilite la captura de pruebas forenses](insider-risk-management-forensic-evidence.md) para dispositivos en línea y sin conexión de su organización.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Consulte [Planeamiento de la administración de riesgos](insider-risk-management-plan.md) internos para obtener información sobre cómo prepararse para habilitar directivas de administración de riesgos internos en su organización.
- Consulte [Introducción a la configuración de administración de riesgos](insider-risk-management-settings.md) internos para configurar la configuración global de las directivas de riesgo internos.
- Consulte [Introducción a la administración de riesgos](insider-risk-management-configure.md) internos para configurar requisitos previos, crear directivas y empezar a recibir alertas.
