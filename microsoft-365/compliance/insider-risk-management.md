---
title: Administración de riesgos internos
description: Obtenga información sobre cómo minimizar el riesgo en su organización con la administración de riesgos de Insider en Microsoft 365.
keywords: Microsoft 365, riesgo para Insiders, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 6045adec673313514243b023dc6ab688387f78d8
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341406"
---
# <a name="insider-risk-management-in-microsoft-365"></a>Administración de riesgos de Insider en Microsoft 365

La administración de riesgos de Insiders es una solución de cumplimiento en Microsoft 365 que ayuda a minimizar los riesgos internos, ya que permite detectar, investigar y actuar en actividades malintencionadas e involuntarias en la organización. Las directivas de riesgo de Insider le permiten definir los tipos de riesgos que se deben identificar y detectar en la organización, como actuar en casos y reasignar casos a la exhibición avanzada de documentos electrónicos de Microsoft si es necesario. Los analistas de riesgos de la organización pueden emprender rápidamente las acciones adecuadas para asegurarse de que los usuarios cumplan los estándares de cumplimiento de la organización.

Vea el vídeo a continuación para obtener información sobre cómo la administración de riesgos de Insider puede ayudar a su organización a evitar, detectar y contener riesgos mientras prioriza los valores de la organización, la cultura y la experiencia del usuario:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Pain Points de riesgo moderno

La administración y minimización de los riesgos en la organización comienza con la comprensión de los tipos de riesgos que se encuentran en el lugar de trabajo moderno. Algunos riesgos están controlados por eventos externos y factores que están fuera de un control directo. Otros riesgos están controlados por eventos internos y actividades de usuario que se pueden minimizar y evitar. Algunos ejemplos son los riesgos de comportamiento ilegal, inapropiado, no autorizado o poco ético y de acciones de los usuarios de la organización. Estos comportamientos incluyen una amplia gama de riesgos internos de los usuarios:

- Pérdidas de datos confidenciales y derrame de datos
- Violaciones de confidencialidad
- Robo de propiedad intelectual (IP)
- Estafa
- Comercio de Insiders
- Violaciones de cumplimiento de normativas

Los usuarios del lugar de trabajo moderno tienen acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos en toda la organización, al tiempo que se cumplen los estándares de privacidad del usuario.

La administración de riesgos de Insiders usa toda la amplitud de los indicadores de servicio y de terceros para ayudarle a identificar, clasificar y actuar con rapidez en la actividad de riesgos. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de Insider le permite definir directivas específicas para identificar los indicadores de riesgo. Estas directivas permiten identificar actividades arriesgadas y actuar para mitigar estos riesgos.

La administración de riesgos de Insider se centra en los siguientes principios:

- **Transparencia**: equilibre la privacidad del usuario frente al riesgo de la organización con la arquitectura de privacidad por diseño.
- **Configurable**: directivas configurables basadas en la industria, la geográfica y los grupos empresariales.
- **Integrado**: flujo de trabajo integrado en las soluciones de cumplimiento de Microsoft 365.
- **Accionable**: proporciona información para habilitar las notificaciones de usuario, las investigaciones de datos y las investigaciones del usuario.

## <a name="workflow"></a>Flujo de trabajo

El flujo de trabajo de administración de riesgos de Insider le ayuda a identificar, investigar y emprender acciones para enfrentar los riesgos internos de la organización. Con las plantillas de directivas centradas, la señalización exhaustiva de actividades en el servicio de Microsoft 365 y las herramientas de administración de alertas y casos, puede usar la información que requiere acción para identificar y actuar rápidamente en un comportamiento arriesgado.

La identificación y resolución de actividades de riesgo internas y problemas de cumplimiento de la administración de riesgos de Insider en Microsoft 365 usa el siguiente flujo de trabajo:

![Flujo de trabajo de administración de riesgos de internación](../media/insider-risk-workflow.png)

### <a name="policies"></a>Directivas

Las [directivas de administración de riesgos de Insider](insider-risk-management-policies.md) se crean usando las directivas predefinidas y las condiciones de directiva que definen qué eventos y indicadores de riesgos se examinan en la organización. Estas condiciones incluyen cómo se usan los indicadores de riesgo para las alertas, qué usuarios se incluyen en la Directiva, qué servicios se priorizan y el período de tiempo de supervisión.

Puede seleccionar entre las siguientes [plantillas de directiva para empezar rápidamente con la administración de riesgos de Insider:

- [Robo de datos al pertenecer a los usuarios](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Pérdidas de datos generales](insider-risk-management-policies.md#general-data-leaks)
- [Pérdidas de datos por usuarios con prioridad (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Pérdidas de datos por usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Infracciones de directivas de seguridad generales (versión preliminar)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Infracciones de la Directiva de seguridad al pertenecer a los usuarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de directivas de seguridad por usuarios con prioridad (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de directivas de seguridad por usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)
- [Lenguaje ofensivo en el correo electrónico](insider-risk-management-policies.md#offensive-language-in-email)

![Panel de directivas de administración de riesgos de Insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Los indicadores de riesgo generan automáticamente alertas que coinciden con las condiciones de la Directiva y se muestran en el [Panel alertas](insider-risk-management-alerts.md). Este panel habilita una vista rápida de todas las alertas que necesitan revisar, abrir alertas a lo largo del tiempo y estadísticas de alertas de la organización. Todas las alertas de Directiva se muestran con la siguiente información para ayudarle a identificar rápidamente el estado de las alertas existentes y nuevas alertas que necesitan acción:

- Estado
- Severity
- Tiempo detectado
- Case
- Estado del caso

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Prioridades

Las nuevas actividades de usuario que necesitan investigación generan automáticamente alertas a las que se asigna un estado de *revisión de necesidades* . Los revisores pueden identificar y revisar rápidamente, evaluar y clasificar estas alertas.

Las alertas se resuelven abriendo un nuevo caso, asignando la alerta a un caso existente o desechando la alerta. Mediante el uso de filtros de alerta, es fácil identificar rápidamente las alertas por estado, gravedad o tiempo detectado. Como parte del proceso de evaluación de prioridades, los revisores pueden ver detalles de las alertas de las actividades identificadas por la Directiva, ver la actividad de los usuarios asociada a la coincidencia de la Directiva, ver la gravedad de la alerta y revisar la información de Perfil de usuario.

![Clasificación de la administración de riesgos de Insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigar

Los [casos](insider-risk-management-cases.md) se crean para las alertas que requieren una revisión y una investigación más detalladas de los detalles de la actividad y las circunstancias en que coincide la Directiva. El **Panel de caso** proporciona una vista general de todos los casos activos, casos abiertos a lo largo del tiempo, y estadísticas de casos para la organización. Los revisores pueden filtrar rápidamente los casos por estado, la fecha en la que se abrió el caso y la fecha en que se actualizó por última vez el caso.

Al seleccionar un caso en el panel del caso, se abre el caso de investigación y revisión. Este paso es el corazón del flujo de trabajo de administración de riesgos de Insider. Esta área es donde se sintetizan las actividades de riesgo, las condiciones de la Directiva, los detalles de las alertas y los detalles del usuario en una vista integrada para los revisores. Las principales herramientas de investigación de esta área son:

- **Actividad de usuario**: la actividad del usuario se muestra automáticamente en un gráfico interactivo que traza las actividades a lo largo del tiempo y por nivel de riesgo para las actividades de riesgo actuales o pasadas. Los revisores pueden filtrar y ver rápidamente todo el historial de riesgos para el usuario y profundizar en actividades específicas para obtener más información.
- **Explorador de contenido**: todos los archivos de datos y mensajes de correo electrónico asociados con actividades de alerta se capturan automáticamente y se muestran en el explorador de contenido. Los revisores pueden filtrar y ver los archivos y los mensajes por origen de datos, tipo de archivo, etiquetas, conversación y muchos más atributos.
- **Notas del caso**: los revisores pueden proporcionar notas para un caso en la sección Notas de caso. Esta lista consolida todas las notas en una vista central e incluye la información enviada por el revisor y la fecha.

![Investigación de administración de riesgos de Insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Acción

Una vez que se han investigado los casos, los revisores pueden actuar rápidamente para resolver el caso o colaborar con otras partes interesadas de riesgo de la organización. Si los usuarios infringen accidental o involuntariamente condiciones de Directiva, se puede enviar una notificación de aviso simple al usuario desde plantillas de notificación que puede personalizar para su organización. Estos avisos pueden servir como recordatorios sencillos o dirigir al usuario a un entrenamiento o guía de refresco para ayudar a evitar un comportamiento arriesgado futuro. Para obtener más información, consulte [plantillas de aviso de administración de riesgos de Insider](insider-risk-management-notices.md).

En las situaciones más graves, es posible que necesite compartir la información del caso de administración de riesgos de Insider con otros revisores o servicios de la organización. La administración de riesgos de Insider se integra estrechamente con otras soluciones de cumplimiento de Microsoft 365 para ayudarle con la resolución de riesgos de un extremo a otro.

- **EDiscovery avanzado**: escalar un caso para investigación le permite transferir datos y administrar el caso a la exhibición avanzada de documentos electrónicos en Microsoft 365. EDiscovery avanzado proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. Permite a los equipos legales administrar todo el flujo de trabajo de notificación de retención legal. Para obtener más información sobre los casos avanzados de eDiscovery, vea [información general sobre EDiscovery avanzado en Microsoft 365](overview-ediscovery-20.md).
- **Servicenow (versión preliminar)**: ServiceNow es una plataforma de informática en la nube que ayuda a las organizaciones a administrar flujos de trabajo digitales para operaciones empresariales. La administración de riesgos de Insider permite compartir alertas de casos con el servicio de ServiceNow y le permite crear incidentes y solicitudes de cambio relacionadas con casos de riesgo de Insider. Para obtener más información sobre cómo compartir información de alertas con ServiceNow, consulte [compartir un caso con servicenow](insider-risk-management-cases.md#share-the-case).
- **Integración de API de administración de office 365 (versión preliminar)**: la administración de riesgos de Insider admite la exportación de información de alertas a servicios de administración de eventos e información de seguridad (Siem) a través de las API de administración de Office 365 Tener acceso a la información de alerta en la plataforma lo mejor que se adapte a los procesos de riesgo de su organización le ofrece más flexibilidad para actuar en las actividades de riesgo. Para obtener más información sobre cómo exportar información de alertas con las API de administración 365 de Office, consulte [exportar alertas](insider-risk-management-settings.md#export-alerts-preview).

## <a name="scenarios"></a>Escenarios

La administración de riesgos de Insiders puede ayudarle a detectar, investigar y emprender acciones para mitigar los riesgos internos de su organización en varios escenarios comunes:

### <a name="data-theft-by-departing-users"></a>Robo de datos al pertenecer a los usuarios

Cuando los usuarios dejan una organización, ya sea voluntariamente o como resultado de la terminación, a menudo hay preocupaciones legítimas de que los datos de la empresa, el cliente y el usuario estén en riesgo. Es posible que los usuarios asuman inocentemente que los datos del proyecto no son de propiedad o que pueden verse tentados a tomar datos de la compañía para obtener un beneficio personal y infringir la Directiva de la compañía y los estándares legales. Las directivas de administración de riesgos de Insider que usan el [robo de datos mediante](insider-risk-management-policies.md#policy-templates) la plantilla de directiva de los usuarios que se desvinculan automáticamente detectan actividades que normalmente están asociadas a este tipo de robo. Con esta Directiva, recibirá automáticamente alertas para actividades sospechosas asociadas con el robo de datos al dejar de usar a los usuarios para que pueda realizar las acciones de investigación adecuadas. Para esta plantilla de Directiva, se necesita configurar un [conector de Microsoft 365](import-hr-data.md) para la organización.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Pérdida intencional o involuntaria de información confidencial o confidencial

En la mayoría de los casos, los usuarios intentan manejar correctamente la información confidencial o confidencial. Pero, en ocasiones, es posible que los usuarios no puedan cometer errores e información fuera de su organización o infringir sus directivas de protección de la información. En otras circunstancias, los usuarios pueden perder o compartir intencionadamente información confidencial y confidencial con malas intenciones y para obtener una ganancia personal potencial. Las directivas de administración de riesgos de Insider creadas mediante las siguientes plantillas de directiva de pérdidas de datos detectan automáticamente las actividades asociadas normalmente al uso compartido de información confidencial.

- [Pérdidas de datos generales](insider-risk-management-policies.md#general-data-leaks)
- [Pérdidas de datos por usuarios con prioridad (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Pérdidas de datos por usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

### <a name="offensive-behavior-that-violates-corporate-policies"></a>Comportamiento ofensivo que infringe las directivas corporativas

Las comunicaciones entre usuarios son a menudo una fuente de infracciones accidentales o malintencionadas de las directivas corporativas. Estas infracciones pueden incluir un lenguaje ofensivo, amenazas y acoso entre usuarios. Este tipo de actividad contribuye a un entorno de trabajo hostil y puede tener como resultado acciones legales contra los usuarios y la organización de mayor tamaño. La administración de riesgos de Insiders usa nuevos clasificadores de 365 de Microsoft integrados y el [lenguaje ofensivo en la plantilla de directiva de correo electrónico](insider-risk-management-policies.md#offensive-language-in-email) para minimizar estos riesgos. Esta plantilla de directiva ayuda a configurar y habilitar rápidamente una directiva para que detecte y le avise automáticamente de este tipo de comportamiento en su organización.

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Infracciones de directivas de seguridad intencionadas o no intencionadas (versión preliminar)

Los usuarios suelen tener un alto grado de control al administrar sus dispositivos en el lugar de trabajo moderno. Esto puede incluir permisos para instalar o desinstalar aplicaciones necesarias en el rendimiento de sus deberes o la capacidad de deshabilitar temporalmente las características de seguridad de dispositivos. Si esta actividad es inadvertida, accidental o malintencionada, esta conducta puede suponer un riesgo para la organización y es importante identificarla y actuar para minimizarla. Para ayudar a identificar estas actividades de seguridad arriesgadas, las siguientes plantillas de infracción de la Directiva de seguridad de Insider Risk Management califican los indicadores de riesgo de seguridad y usan alertas de la protección contra amenazas avanzada (ATP) de Microsoft defender para proporcionar información sobre las actividades relacionadas con la seguridad:

- [Infracciones de directivas de seguridad generales (versión preliminar)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Infracciones de la Directiva de seguridad al pertenecer a los usuarios (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Infracciones de directivas de seguridad por usuarios con prioridad (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Infracciones de directivas de seguridad por usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Directivas para los usuarios en función de la ubicación, el nivel de acceso o el historial de riesgos (versión preliminar)

Los usuarios de la organización pueden tener distintos niveles de riesgo en función de su posición, el nivel de acceso a la información confidencial o el historial de riesgos. Esto puede incluir a los miembros del equipo directivo de su organización, los administradores de ti que tienen numerosos datos y privilegios de acceso a la red, o bien a los usuarios con un historial de actividades arriesgadas. En estos casos, la inspección más detallada y la puntuación más agresiva son importantes para ayudar a exponer las alertas a la investigación y a la acción rápida. Para ayudar a identificar las actividades arriesgadas para estos tipos de usuarios, puede crear grupos de usuarios prioritarios y crear directivas a partir de las siguientes plantillas de directiva:

- [Infracciones de directivas de seguridad por usuarios con prioridad (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Pérdidas de datos por usuarios con prioridad (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Acciones y comportamientos de usuarios descontentos (versión preliminar)

Los eventos de esfuerzo de empleo pueden afectar al comportamiento del usuario de varias maneras relacionadas con los riesgos de Insider. Estos sobrecargadores pueden ser una revisión deficiente del rendimiento, una degradación de la posición o el usuario que se coloca en un plan de revisión del rendimiento. Aunque la mayoría de los usuarios no responden malintencionadamente a estos eventos, la tensión de estas acciones puede dar lugar a que algunos usuarios tomen acciones que, por lo general, no tienen en cuenta en circunstancias normales. Para ayudar a identificar estos tipos de actividades de riesgo, las siguientes plantillas de directiva de administración de riesgos de Insider usan el conector de 365 de RRHH de Microsoft y comienzan los indicadores de riesgo relacionados con comportamientos que se pueden producir cerca de los eventos Stressor de empleo:

- [Pérdidas de datos por usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Infracciones de directivas de seguridad por usuarios descontentos (versión preliminar)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Consulte [planeación de la administración de riesgos de Insiders](insider-risk-management-plan.md) para obtener más sobre cómo prepararse para habilitar directivas de administración de riesgos de Insider en su organización.
- Vea Introducción a la configuración de la [Administración de riesgos de Insider](insider-risk-management-settings.md) para establecer la configuración global de las directivas de riesgos de Insider.
- Consulte Introducción a la [Administración de riesgos de Insider](insider-risk-management-configure.md) para configurar los requisitos previos, crear directivas y empezar a recibir alertas.
