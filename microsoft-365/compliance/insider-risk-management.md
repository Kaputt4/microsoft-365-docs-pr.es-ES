---
title: Información sobre riesgos internos de Microsoft
description: Obtenga información sobre cómo ayudar a minimizar los riesgos en su organización con la administración de riesgos interno en Microsoft 365.
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
ms.openlocfilehash: ceb35fa9e89a5393500cecb82e52f44852e47b6f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094671"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>Más información sobre la administración de riesgos interno en Microsoft 365

La administración de riesgos internos es una solución de cumplimiento de Microsoft 365 que ayuda a minimizar los riesgos internos al permitirle detectar, investigar y actuar sobre actividades malintencionadas e involuntarias en su organización. Las directivas de riesgo de Insider le permiten definir los tipos de riesgos que se deben identificar y detectar en su organización, incluido actuar en casos y escalar los casos a eDiscovery avanzado de Microsoft si es necesario. Los analistas de riesgos de su organización pueden tomar rápidamente las medidas adecuadas para asegurarse de que los usuarios cumplen con los estándares de cumplimiento de la organización.

Vea el vídeo siguiente para obtener información sobre cómo la administración de riesgos de Insider puede ayudar a su organización a prevenir, detectar y contener riesgos a la vez que prioriza los valores de la organización, la cultura y la experiencia del usuario:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Puntos de riesgo modernos

La administración y minimización de riesgos en su organización comienza por comprender los tipos de riesgos que se encuentran en el lugar de trabajo moderno. Algunos riesgos están controlados por eventos externos y factores que están fuera del control directo. Otros riesgos están controlados por eventos internos y actividades de usuario que se pueden minimizar y evitar. Algunos ejemplos son riesgos por comportamientos y acciones ilegales, inapropiados, no autorizados o no éticos por parte de los usuarios de su organización. Estos comportamientos incluyen una amplia gama de riesgos internos de los usuarios:

- Pérdidas de datos confidenciales y pérdidas de datos
- Violaciones de la confidencialidad
- Robo de propiedad intelectual (IP)
- Fraude
- Insider trading
- Infracciones de cumplimiento normativo

Los usuarios del área de trabajo moderna tienen acceso para crear, administrar y compartir datos en una amplia variedad de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización y, al mismo tiempo, cumplir con los estándares de privacidad del usuario.

La administración de riesgos de Insider usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, recortar y actuar rápidamente en la actividad de riesgo. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos interno le permite definir directivas específicas para identificar indicadores de riesgo. Estas directivas permiten identificar actividades de riesgo y actuar para mitigar estos riesgos.

La administración de riesgos de Insider se centra en los siguientes principios:

- **Transparencia: equilibra** la privacidad del usuario frente al riesgo de la organización con la arquitectura de privacidad por diseño.
- **Configurable:** directivas configurables basadas en grupos empresariales, geográficos y del sector.
- **Integrado:** flujo de trabajo integrado en las soluciones de cumplimiento de Microsoft 365.
- **Acción:** proporciona información para habilitar las notificaciones de usuario, las investigaciones de datos y las investigaciones de usuarios.

## <a name="workflow"></a>Flujo de trabajo

El flujo de trabajo de administración de riesgos internos le ayuda a identificar, investigar y tomar medidas para abordar los riesgos internos de su organización. Con las plantillas de directiva centradas, la señalización de actividad completa en todo el servicio de Microsoft 365 y las herramientas de administración de alertas y casos, puede usar información útil para identificar y actuar rápidamente en comportamientos de riesgo.

La identificación y resolución de actividades de riesgos internos y problemas de cumplimiento con la administración de riesgos internos en Microsoft 365 usa el siguiente flujo de trabajo:

![Flujo de trabajo de administración de riesgos de Insider](../media/insider-risk-workflow.png)

### <a name="policies"></a>Directivas

[Las directivas de administración](insider-risk-management-policies.md) de riesgos de Insider se crean con plantillas predefinidas y condiciones de directiva que definen qué eventos desencadenantes e indicadores de riesgo se examinan en la organización. Estas condiciones incluyen cómo se usan los indicadores de riesgo para las alertas, qué usuarios se incluyen en la directiva, qué servicios se priorizan y el período de tiempo de supervisión.

Puede seleccionar entre las siguientes[plantillas de directiva para empezar rápidamente con la administración de riesgos interno:

- [Robo de datos al salir de usuarios](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Pérdidas de datos generales](insider-risk-management-policies.md#general-data-leaks)
- [Pérdidas de datos por usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Pérdidas de datos de usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Infracciones de directivas de seguridad generales (versión preliminar)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Infracciones de directivas de seguridad al abandonar usuarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![Panel de directivas de administración de riesgos de Insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Las alertas se generan automáticamente mediante indicadores de riesgo que coinciden con las condiciones de la directiva y se muestran en el panel [alertas.](insider-risk-management-alerts.md) Este panel permite una vista rápida de todas las alertas que necesitan revisión, alertas abiertas a lo largo del tiempo y estadísticas de alertas para su organización. Todas las alertas de directiva se muestran con la siguiente información para ayudarle a identificar rápidamente el estado de las alertas existentes y las alertas nuevas que necesitan acción:

- Estado
- Severity
- Tiempo detectado
- Case
- Estado del caso

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triage

Las nuevas actividades de usuario que necesitan investigación generan automáticamente alertas a las que se les asigna un *estado de revisión de* necesidades. Los revisores pueden identificar y revisar, evaluar y evaluar rápidamente estas alertas.

Las alertas se resuelven abriendo un nuevo caso, asignando la alerta a un caso existente o descartando la alerta. Con los filtros de alerta, es fácil identificar rápidamente las alertas por estado, gravedad u tiempo detectados. Como parte del proceso de evaluación, los revisores pueden ver los detalles de las alertas de las actividades identificadas por la directiva, ver la actividad de usuario asociada con la coincidencia de directiva, ver la gravedad de la alerta y revisar la información del perfil de usuario.

![Evaluación de la administración de riesgos de Insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigar

[Se crean](insider-risk-management-cases.md) casos para alertas que requieren una revisión e investigación más profundas de los detalles de la actividad y las circunstancias en torno a la coincidencia de la directiva. El **panel Caso** proporciona una vista general de todos los casos activos, los casos abiertos a lo largo del tiempo y las estadísticas de casos de la organización. Los revisores pueden filtrar rápidamente los casos por estado, la fecha en que se abrió el caso y la fecha en que se actualizó el caso por última vez.

Al seleccionar un caso en el panel del caso, se abre el caso para su investigación y revisión. Este paso es el corazón del flujo de trabajo de administración de riesgos interno. Esta área es donde las actividades de riesgo, las condiciones de directiva, los detalles de alertas y los detalles del usuario se sintetizan en una vista integrada para los revisores. Las principales herramientas de investigación en esta área son:

- **Actividad de usuario:** la actividad del usuario se muestra automáticamente en un gráfico interactivo que traza las actividades a lo largo del tiempo y por nivel de riesgo para las actividades de riesgo actuales o pasadas. Los revisores pueden filtrar y ver rápidamente todo el historial de riesgos del usuario y explorar actividades específicas para obtener más detalles.
- **Explorador de contenido:** todos los archivos de datos y mensajes de correo electrónico asociados con actividades de alerta se capturan automáticamente y se muestran en el Explorador de contenido. Los revisores pueden filtrar y ver archivos y mensajes por origen de datos, tipo de archivo, etiquetas, conversación y muchos más atributos.
- **Notas del caso:** los revisores pueden proporcionar notas para un caso en la sección Notas del caso. Esta lista consolida todas las notas en una vista central e incluye información de revisor y fecha enviada.

![Investigación de administración de riesgos de Insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Action

Una vez que se investigan los casos, los revisores pueden actuar rápidamente para resolver el caso o colaborar con otras partes interesadas de riesgos de su organización. Si los usuarios infringen accidentalmente o inadvertidamente las condiciones de la directiva, se puede enviar un aviso simple al usuario desde plantillas de aviso que puede personalizar para su organización. Estos avisos pueden servir como recordatorios simples o pueden dirigir al usuario a un curso de actualización o instrucciones para ayudar a evitar comportamientos de riesgo futuros. Para obtener más información, consulta plantillas de aviso de [administración de riesgos de Insider.](insider-risk-management-notices.md)

En las situaciones más graves, es posible que deba compartir la información de casos de administración de riesgos interno con otros revisores o servicios de su organización. La administración de riesgos de Insider está estrechamente integrada con otras soluciones de cumplimiento de Microsoft 365 para ayudarle con la resolución de riesgos de un extremo a otro.

- **EDiscovery avanzado:** escalar un caso para investigación le permite transferir datos y la administración del caso a eDiscovery avanzado en Microsoft 365. EDiscovery avanzado proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de su organización. Permite a los equipos legales administrar todo el flujo de trabajo de notificación de retención legal. Para obtener más información sobre los casos de eDiscovery avanzado, vea Información general sobre [eDiscovery avanzado en Microsoft 365.](overview-ediscovery-20.md)
- **ServiceNow (versión preliminar):** ServiceNow es una plataforma informática en la nube popular que ayuda a las organizaciones a administrar flujos de trabajo digitales para las operaciones empresariales. La administración de riesgos de Insider admite el uso compartido de alertas de casos con el servicio ServiceNow y le permite crear incidentes y cambiar solicitudes relacionadas con casos de riesgo de insider individuales. Para obtener más información sobre cómo compartir información de alertas con ServiceNow, vea [Compartir un caso con ServiceNow](insider-risk-management-cases.md#share-the-case).
- Integración de las API de administración de **Office 365 (versión preliminar):** la administración de riesgos de Insider admite la exportación de información de alertas a los servicios de administración de eventos e información de seguridad (SIEM) a través de las API de administración de Office 365. Tener acceso a la información de alertas en la plataforma que mejor se adapte a los procesos de riesgo de su organización le ofrece más flexibilidad en la forma de actuar sobre las actividades de riesgo. Para obtener más información sobre cómo exportar información de alertas con las API de administración de Office 365, vea [Exportar alertas.](insider-risk-management-settings.md#export-alerts-preview)

>[!NOTE]
>Gracias por sus comentarios y soporte técnico durante la vista previa del conector ServiceNow. Hemos decidido finalizar la versión preliminar del conector ServiceNow y dejar de admitir la administración de riesgos de Insider el 30 de noviembre de 2020. Estamos evaluando activamente métodos alternativos para proporcionar a los clientes la integración de ServiceNow en la administración de riesgos interno.

## <a name="scenarios"></a>Escenarios

La administración de riesgos internos puede ayudarle a detectar, investigar y tomar medidas para mitigar los riesgos internos de su organización en varios escenarios comunes:

### <a name="data-theft-by-departing-users"></a>Robo de datos al salir de usuarios

Cuando los usuarios abandonan una organización, ya sea de forma voluntaria o como resultado de la terminación, a menudo hay preocupaciones legítimas por las que los datos de la empresa, el cliente y el usuario están en riesgo. Los usuarios pueden suponer de manera ileuta que los datos del proyecto no son propiedad de la empresa o pueden sentirse tentados a tomar datos de la empresa para obtener ganancias personales y infringiendo la directiva de la empresa y los estándares legales. Las directivas de administración [](insider-risk-management-policies.md#policy-templates) de riesgos de Insider que usan el robo de datos al salir de la plantilla de directiva de usuarios detectan automáticamente las actividades normalmente asociadas a este tipo de robo. Con esta directiva, recibirá automáticamente alertas de actividades sospechosas asociadas con el robo de datos al salir de los usuarios para que pueda realizar las acciones de investigación adecuadas. Es necesario configurar un conector de Recursos Humanos de [Microsoft 365](import-hr-data.md) para su organización para esta plantilla de directiva.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Pérdida intencionada o no intencionada de información confidencial o confidencial

En la mayoría de los casos, los usuarios intentan controlar correctamente la información confidencial. Pero, en ocasiones, los usuarios pueden equivocarse y la información se comparte accidentalmente fuera de su organización o infringiendo las directivas de protección de la información. En otras circunstancias, los usuarios pueden filtrar intencionadamente o compartir información confidencial y confidencial con intención malintencionada y para posibles ganancias personales. Las directivas de administración de riesgos internas creadas con las siguientes plantillas de directiva de pérdida de datos detectan automáticamente actividades asociadas normalmente con el uso compartido de información confidencial o confidencial:

- [Pérdidas de datos generales](insider-risk-management-policies.md#general-data-leaks)
- [Pérdidas de datos por usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Pérdidas de datos de usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Infracciones de directivas de seguridad intencionadas o no intencionadas (versión preliminar)

Los usuarios suelen tener un gran grado de control al administrar sus dispositivos en el lugar de trabajo moderno. Esto puede incluir permisos para instalar o desinstalar aplicaciones necesarias en el rendimiento de sus tareas o la capacidad de deshabilitar temporalmente las características de seguridad del dispositivo. Independientemente de si esta actividad es involuntaria, accidental o malintencionada, esta conducta puede suponer un riesgo para su organización y es importante identificarla y actuar para minimizarla. Para ayudar a identificar estas actividades de seguridad de riesgo, las siguientes plantillas de infracción de directivas de seguridad de administración de riesgos interno obtienen indicadores de riesgo de seguridad y usan alertas de Microsoft Defender para puntos de conexión para proporcionar información sobre actividades relacionadas con la seguridad:

- [Infracciones de directivas de seguridad generales (versión preliminar)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Infracciones de directivas de seguridad al abandonar usuarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Directivas para usuarios basadas en la posición, el nivel de acceso o el historial de riesgos (versión preliminar)

Los usuarios de su organización pueden tener distintos niveles de riesgo en función de su posición, nivel de acceso a información confidencial o historial de riesgos. Esto puede incluir miembros del equipo directivo ejecutivo de su organización, administradores de TI con amplios privilegios de acceso a la red y datos, o usuarios con un historial pasado de actividades de riesgo. En estas circunstancias, es importante una inspección más minuciosa y una puntuación de riesgo más agresiva para ayudar a que se avisa a la superficie para investigar y tomar medidas rápidas. Para ayudar a identificar actividades de riesgo para estos tipos de usuarios, puede crear grupos de usuarios prioritarios y crear directivas a partir de las siguientes plantillas de directiva:

- [Infracciones de directivas de seguridad por parte de usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Pérdidas de datos por usuarios prioritarios (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Acciones y comportamientos de usuarios descontentos (versión preliminar)

Los eventos de tensión laboral pueden afectar al comportamiento del usuario de varias maneras relacionadas con los riesgos de insider. Estos estresores pueden ser una revisión de rendimiento deficiente, una degradación de la posición o la colocación del usuario en un plan de revisión del rendimiento. Aunque la mayoría de los usuarios no responde de forma malintencionada a estos eventos, el esfuerzo de estas acciones puede hacer que algunos usuarios tomen medidas que normalmente no consideren durante circunstancias normales. Para ayudar a identificar estos tipos de actividades de riesgo, las siguientes plantillas de directiva de administración de riesgos interno usan el conector de RECURSOS de Microsoft 365 y comienzan a puntuar indicadores de riesgo relacionados con comportamientos que pueden producirse cerca de eventos de factores de estrés de empleo:

- [Pérdidas de datos de usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Infracciones de directivas de seguridad por parte de usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Vea [el plan para la administración de riesgos](insider-risk-management-plan.md) internas para saber cómo prepararse para habilitar las directivas de administración de riesgos internas en su organización.
- Consulta Introducción a las opciones de administración de riesgos de [Insider](insider-risk-management-settings.md) para configurar la configuración global de las directivas de riesgo interno.
- Consulte Introducción a la administración de riesgos [de Insider](insider-risk-management-configure.md) para configurar requisitos previos, crear directivas y empezar a recibir alertas.
