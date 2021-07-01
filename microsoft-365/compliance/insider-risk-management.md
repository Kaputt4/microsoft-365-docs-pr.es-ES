---
title: Información sobre riesgos internos de Microsoft
description: Obtenga información sobre cómo ayudar a minimizar los riesgos en su organización con la administración de riesgos de insider en Microsoft 365.
keywords: Microsoft 365, riesgo interno, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 1864c34f1e7bb17decfaeb2057dfff463a33b37c
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226352"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>Obtenga información sobre la administración de riesgos de insider en Microsoft 365

La administración de riesgos de Insider es una solución de cumplimiento en Microsoft 365 que ayuda a minimizar los riesgos internos al permitirle detectar, investigar y actuar sobre actividades malintencionadas e involuntarias en su organización. Las directivas de riesgo de Insider le permiten definir los tipos de riesgos que se deben identificar y detectar en su organización, incluido actuar en casos y escalar los casos a Microsoft Advanced eDiscovery si es necesario. Los analistas de riesgos de la organización pueden tomar rápidamente las acciones adecuadas para asegurarse de que los usuarios cumplen con los estándares de cumplimiento de la organización.

Vea el vídeo siguiente para obtener información sobre cómo la administración de riesgos de insider puede ayudar a su organización a prevenir, detectar y contener riesgos al priorizar los valores de la organización, la cultura y la experiencia del usuario:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Puntos de dolor de riesgo modernos

La administración y minimización de los riesgos en su organización empieza con la comprensión de los tipos de riesgos que se encuentran en Modern Workplace. Algunos riesgos se controlan por eventos externos y factores que están fuera del control directo. Otros riesgos se deben a eventos internos y actividades de usuario que se pueden minimizar y evitar. Algunos ejemplos son riesgos de comportamientos y acciones ilegales, inapropiados, no autorizados o no éticos por parte de los usuarios de su organización. Estos comportamientos incluyen una amplia gama de riesgos internos de los usuarios:

- Filtraciones de datos confidenciales y pérdida de datos
- Infracciones de confidencialidad
- Robo de propiedad intelectual
- Fraude
- Tráfico de información privilegiada
- Infracciones de cumplimiento normativo

Los usuarios en el lugar de trabajo moderno tienen acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, al tiempo que también se reúnen con los estándares de privacidad de los usuarios.

La administración de riesgos de Insider usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, recortar y actuar rápidamente en la actividad de riesgo. Al usar registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de insider permite definir directivas específicas para identificar indicadores de riesgo. Estas directivas permiten identificar actividades arriesgadas y actuar para mitigar estos riesgos.

La administración de riesgos de Insider se centra en los siguientes principios:

- **Transparencia: equilibra** la privacidad del usuario frente al riesgo de la organización con la arquitectura de privacidad por diseño.
- **Configurable:** directivas configurables basadas en grupos industriales, geográficos y empresariales.
- **Integrado:** flujo de trabajo integrado en Microsoft 365 de cumplimiento normativo.
- **Actionable:** proporciona información para habilitar las notificaciones de revisor, las investigaciones de datos y las investigaciones de usuario.

## <a name="identifying-potential-risks-with-analytics-preview"></a>Identificación de posibles riesgos con análisis (versión preliminar)

Los análisis de riesgos internos le permiten realizar una evaluación de los posibles riesgos internos en su organización sin necesidad de configurar ninguna directiva de riesgos internos. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar. Esta evaluación también puede ayudarle a determinar las necesidades de licencias adicionales o la optimización futura de las directivas de riesgos internas existentes.

Para obtener más información sobre el análisis de riesgos de insider, consulte Configuración de administración de riesgos [de Insider: Analytics](insider-risk-management-settings.md#analytics-preview).

## <a name="workflow"></a>Flujo de trabajo

El flujo de trabajo de administración de riesgos internos le ayuda a identificar, investigar y tomar medidas para abordar los riesgos internos de la organización. Con plantillas de directiva centradas, señalización de actividad completa en todo el servicio de Microsoft 365 y herramientas de administración de alertas y casos, puede usar información útil para identificar y actuar rápidamente en comportamientos de riesgo.

La identificación y resolución de actividades de riesgo interno y problemas de cumplimiento con la administración de riesgos internos en Microsoft 365 usa el siguiente flujo de trabajo:

![Flujo de trabajo de la administración de riesgos internos](../media/insider-risk-workflow.png)

### <a name="policies"></a>Directivas

[Las directivas de administración](insider-risk-management-policies.md) de riesgos de Insider se crean con plantillas predefinidas y condiciones de directiva que definen qué eventos desencadenantes e indicadores de riesgo se examinan en su organización. Estas condiciones incluyen cómo se usan los indicadores de riesgo para las alertas, qué usuarios se incluyen en la directiva, qué servicios se priorizan y el período de tiempo de supervisión.

Puede seleccionar entre las siguientes plantillas de directiva para empezar rápidamente con la administración de riesgos de insider:

- [Robo de datos por parte de los usuarios que abandonan la organización](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Filtraciones de datos generales](insider-risk-management-policies.md#general-data-leaks)
- [Filtración de datos por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Filtraciones de datos por parte de usuarios inconformes (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Infracciones generales de la directiva de seguridad (versión preliminar)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de la directiva de seguridad por parte de usuarios inconformes (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![Panel de directiva de administración de riesgos internos](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Las alertas se generan automáticamente mediante indicadores de riesgo que coinciden con las condiciones de la directiva y se muestran en el panel [Alertas.](insider-risk-management-alerts.md) Este panel ofrece una vista rápida de todas las alertas que se deben revisar, alertas abiertas a lo largo del tiempo y estadísticas de alertas de la organización. Todas las alertas de directiva se muestran con la siguiente información para ayudarle a identificar rápidamente el estado de las alertas existentes y las alertas nuevas que necesitan acción:

- Estado
- Gravedad
- Tiempo detectado
- Case
- Estado del caso

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triage

Las nuevas actividades de usuario que necesitan investigación generan automáticamente alertas a las que se les asigna el *estado Necesita revisión.* Los revisores pueden identificar y revisar, evaluar y evaluar rápidamente estas alertas.

Para resolver las alertas, se abre un nuevo caso, se asigna la alerta a un caso existente o se descarta la alerta. Con los filtros de alerta, es fácil identificar rápidamente las alertas por estado, gravedad o tiempo detectados. Como parte del proceso de evaluación, los revisores pueden ver los detalles de alerta de las actividades identificadas por la directiva, ver la actividad de usuario asociada con la coincidencia de directiva, ver la gravedad de la alerta y revisar la información del perfil de usuario.

![Evaluación de la administración de riesgos de Insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigar

[Los casos](insider-risk-management-cases.md) se crean para alertas que requieren una revisión e investigación más profundas de los detalles y circunstancias de la actividad en torno a la coincidencia de directiva. El **panel de casos** ofrece una vista integral de todos los casos activos, casos abiertos a lo largo del tiempo y estadísticas de casos para la organización. Los revisores pueden filtrar rápidamente los casos por estado, la fecha en que se abrió el caso y la fecha en que se actualizó por última vez el caso.

Si se selecciona un caso en el panel de casos, se abre el caso para su investigación y revisión. Este paso es el corazón del flujo de trabajo de administración de riesgos de insider. Esta área es donde las actividades de riesgo, las condiciones de directiva, los detalles de alertas y los detalles del usuario se sintetizan en una vista integrada para revisores. Las herramientas de investigación principales en esta área son:

- **Actividad de usuario:** la actividad del usuario se muestra automáticamente en un gráfico interactivo que traza las actividades con el tiempo y por nivel de riesgo para las actividades de riesgo actuales o pasadas. Los revisores pueden filtrar y ver rápidamente todo el historial de riesgos para el usuario y profundizar en actividades específicas para obtener más detalles.
- **Explorador de contenido:** todos los archivos de datos y mensajes de correo electrónico asociados con actividades de alerta se capturan y muestran automáticamente en el explorador de contenido. Los revisores pueden filtrar y ver archivos y mensajes por origen de datos, tipo de archivo, etiquetas, conversación y muchos más atributos.
- **Notas del caso:** los revisores pueden proporcionar notas para un caso en la sección Notas del caso. Esta lista consolida todas las notas en una vista central e incluye información de revisor y fecha enviada.

![Investigación de administración de riesgos insider](../media/insider-risk-investigate.png)

Además, el nuevo registro de [auditoría (versión preliminar)](insider-risk-management-audit-log.md) permite mantenerse informado de las acciones realizadas en las características de administración de riesgos internas. Este recurso permite una revisión independiente de las acciones realizadas por los usuarios asignados a uno o varios grupos de roles de administración de riesgos insider.

### <a name="action"></a>Acción

Una vez que se investigan los casos, los revisores pueden actuar rápidamente para resolver el caso o colaborar con otras partes interesadas en riesgos de la organización. Si los usuarios infringen accidentalmente o inadvertidamente las condiciones de la directiva, se puede enviar un aviso simple al usuario desde plantillas de aviso que puede personalizar para su organización. Estos avisos pueden servir como recordatorios sencillos o pueden dirigir al usuario a cursos de actualización o instrucciones para ayudar a evitar comportamientos de riesgo futuros. Para más información, consulte [plantillas de notificación de administración de riesgos internos](insider-risk-management-notices.md).

En las situaciones más graves, es posible que deba compartir la información de casos de administración de riesgos confidenciales con otros revisores o servicios de su organización. La administración de riesgos de Insider está estrechamente integrada con otras Microsoft 365 de cumplimiento normativo para ayudarle con la resolución de riesgos de un extremo a otro.

- **Advanced eDiscovery:** escalar un caso de investigación le permite transferir datos y la administración del caso a Advanced eDiscovery en Microsoft 365. eDiscovery avanzado proporciona un flujo de trabajo de un extremo a otro para conservar, recopilar, revisar, analizar y exportar contenido que responda a las investigaciones internas y externas de su organización. Permite que los equipos legales administren todo el flujo de trabajo de notificaciones de suspensión legal. Para obtener más información sobre los casos de eDiscovery avanzado, consulte [Información general sobre la exhibición avanzada de documentos electrónicos en Microsoft 365](overview-ediscovery-20.md).
- Office 365 integración de api de administración de eventos **(versión preliminar):** la administración de riesgos de Insider admite la exportación de información de alertas a los servicios de administración de eventos y de información de seguridad (SIEM) a través de las API de administración de Office 365 administración. Tener acceso a la información de alertas en la plataforma lo mejor que se adapta a los procesos de riesgo de su organización le ofrece más flexibilidad en cómo actuar en las actividades de riesgo. Para obtener más información sobre cómo exportar información de alerta con Office 365 API de administración, vea [Exportar alertas](insider-risk-management-settings.md#export-alerts-preview).

> [!NOTE]
> Gracias por sus comentarios y soporte técnico durante la vista previa del conector servicenow. El 30 de noviembre de 2020 hemos decidido finalizar la versión preliminar del conector ServiceNow y dejar de admitir la administración de riesgos de insider. Estamos evaluando activamente métodos alternativos para proporcionar a los clientes la integración de ServiceNow en la administración de riesgos de insider.

## <a name="scenarios"></a>Escenarios

La administración de riesgos de Insider puede ayudarle a detectar, investigar y tomar medidas para mitigar los riesgos internos de su organización en varios escenarios comunes:

### <a name="data-theft-by-departing-users"></a>Robo de datos por parte de los usuarios que abandonan la organización

Cuando los usuarios abandonan una organización, ya sea de forma voluntaria o como resultado de la terminación, a menudo hay preocupaciones legítimas de que los datos de la empresa, el cliente y el usuario están en riesgo. Los usuarios pueden asumir inocentemente que los datos del proyecto no son propietarios, o pueden verse tentados a tomar datos de la compañía para obtener ganancias personales y infringiendo la directiva de la compañía y los estándares legales. Las directivas de administración de riesgos de Insider que usan la [plantilla de](insider-risk-management-policies.md#policy-templates) directiva Robo de datos al salir de los usuarios detectan automáticamente las actividades asociadas normalmente a este tipo de robo. Con esta directiva, recibirá automáticamente alertas de actividades sospechosas asociadas con el robo de datos al salir de los usuarios para que pueda realizar las acciones de investigación adecuadas. Es necesario configurar [un Microsoft 365 de](import-hr-data.md) recursos humanos de la organización para esta plantilla de directiva.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Filtración intencionada o no intencionada de información confidencial o confidencial

En la mayoría de los casos, los usuarios intentan controlar correctamente la información confidencial o confidencial. Pero en ocasiones, los usuarios pueden cometer errores y la información se comparte accidentalmente fuera de la organización o en violación de las directivas de protección de la información. En otras circunstancias, los usuarios pueden filtrar intencionadamente o compartir información confidencial y confidencial con intenciones malintencionadas y con potencial ganancia personal. Las directivas de administración de riesgos insider creadas con las siguientes plantillas de directiva de pérdida de datos detectan automáticamente actividades asociadas normalmente con el uso compartido de información confidencial o confidencial:

- [Filtraciones de datos generales](insider-risk-management-policies.md#general-data-leaks)
- [Filtración de datos por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Filtraciones de datos por parte de usuarios inconformes (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Infracciones intencionadas o involuntarias de directivas de seguridad (versión preliminar)

Los usuarios suelen tener un gran grado de control al administrar sus dispositivos en el lugar de trabajo moderno. Este control puede incluir permisos para instalar o desinstalar aplicaciones necesarias en el rendimiento de sus funciones o la capacidad de deshabilitar temporalmente las características de seguridad del dispositivo. Independientemente de si esta actividad es involuntaria, accidental o malintencionada, esta conducta puede suponer un riesgo para la organización y es importante identificar y actuar para minimizar. Para ayudar a identificar estas actividades de seguridad de riesgo, las siguientes plantillas de infracción de directivas de seguridad de administración de riesgos insider obtienen indicadores de riesgo de seguridad y usan Alertas de Microsoft Defender para endpoints para proporcionar información sobre actividades relacionadas con la seguridad:

- [Infracciones generales de la directiva de seguridad (versión preliminar)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de la directiva de seguridad por parte de usuarios inconformes (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Directivas para usuarios en función de la posición, el nivel de acceso o el historial de riesgos (versión preliminar)

Los usuarios de la organización pueden tener diferentes niveles de riesgo según su posición, nivel de acceso a información confidencial o historial de riesgos. Esta estructura puede incluir miembros del equipo de liderazgo ejecutivo de su organización, administradores de TI con amplios privilegios de acceso a la red y datos, o usuarios con un historial pasado de actividades arriesgadas. En estas circunstancias, una inspección más estrecha y una puntuación de riesgos más agresiva son importantes para ayudar a las alertas de superficie para la investigación y la acción rápida. Para ayudar a identificar actividades de riesgo para este tipo de usuarios, puede crear grupos de usuarios prioritarios y crear directivas a partir de las siguientes plantillas de directiva:

- [Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Filtración de datos por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Acciones y comportamientos de usuarios inconformes (versión preliminar)

El empleo subraya que los eventos pueden afectar al comportamiento de los usuarios de varias maneras relacionadas con los riesgos de insider. Estos estresores pueden ser una revisión de rendimiento deficiente, una degradación de posición o la colocación del usuario en un plan de revisión de rendimiento. Aunque la mayoría de los usuarios no responden malintencionadamente a estos eventos, el estrés de estas acciones puede provocar que algunos usuarios realicen acciones que normalmente no consideren en circunstancias normales. Para ayudar a identificar estos tipos de actividades arriesgadas, las siguientes plantillas de directiva de administración de riesgos de insider usan el conector de recursos humanos de Microsoft 365 y comienzan a puntuar indicadores de riesgo relacionados con comportamientos que pueden producirse cerca de eventos de estrés laboral:

- [Filtraciones de datos por parte de usuarios inconformes (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Infracciones de la directiva de seguridad por parte de usuarios inconformes (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Consulte [Plan for insider risk management](insider-risk-management-plan.md) para obtener información sobre cómo prepararse para habilitar las directivas de administración de riesgos de insider en su organización.
- Consulta Introducción a las opciones de administración de riesgos de [insider](insider-risk-management-settings.md) para configurar la configuración global para las directivas de riesgo de insider.
- Consulte [Introducción a la administración de riesgos de insider](insider-risk-management-configure.md) para configurar requisitos previos, crear directivas y empezar a recibir alertas.
