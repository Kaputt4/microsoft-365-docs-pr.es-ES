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
ms.collection: m365-security-compliance
ms.openlocfilehash: 8b7d60d8b1a3c7295dbeda93c9f2e017ca6f9282
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327886"
---
# <a name="insider-risk-management-in-microsoft-365"></a>Administración de riesgos de Insider en Microsoft 365

La administración de riesgos de Insider es una solución en Microsoft 365 que contribuye a minimizar los riesgos internos, ya que permite detectar, investigar y realizar acciones en actividades de riesgo de la organización. Las directivas personalizadas le permiten detectar y realizar acciones en actividades malintencionadas e involuntarias de riesgos en su organización, incluidos el reajuste de casos a la exhibición avanzada de documentos electrónicos de Microsoft si es necesario. Los analistas de riesgos de la organización pueden emprender rápidamente las acciones adecuadas para asegurarse de que los usuarios cumplan los estándares de cumplimiento de la organización.

Vea el vídeo a continuación para obtener información sobre cómo la administración de riesgos de Insider puede ayudar a su organización a prevenir, detectar y contener riesgos, a la vez que prioriza los valores de la organización, la cultura y la experiencia de los empleados:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Pain Points de riesgo moderno

La administración y minimización de los riesgos en la organización comienza con la comprensión de los tipos de riesgos que se encuentran en el lugar de trabajo moderno. Algunos riesgos están controlados por eventos externos y factores y se encuentran fuera del control directo. Otros riesgos están controlados por eventos internos y actividades de los empleados que pueden eliminarse y evitarse. Algunos ejemplos son los riesgos de comportamiento ilegal, inapropiado, no autorizado o poco ético y acciones de empleados y directores. Estos comportamientos incluyen una amplia gama de riesgos internos de los empleados:

- Pérdidas de datos confidenciales y derrame de datos
- Violaciones de confidencialidad
- Robo de propiedad intelectual (IP)
- Estafa
- Comercio de Insiders
- Violaciones de cumplimiento de normativas

Los empleados en el lugar de trabajo moderno tienen acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos en toda la organización, al tiempo que cumplen los estándares de privacidad de los empleados.

La administración de riesgos de Insider de Microsoft 365 usa toda la amplitud de los indicadores de servicio y de terceros para ayudarle a identificar, clasificar y realizar acciones en la actividad de riesgos rápidamente. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos de Insider le permite definir directivas específicas para identificar los indicadores de riesgo. Estas directivas le permiten identificar actividades arriesgadas y emprender acciones para mitigar estos riesgos.

La administración de riesgos de Insider se centra en los siguientes principios:

- **Transparencia**: equilibre la privacidad de los empleados frente al riesgo de la organización con la arquitectura de privacidad por diseño.
- **Configurable**: directivas configurables basadas en la industria, la geográfica y los grupos empresariales.
- **Integrado**: flujo de trabajo integrado en las soluciones de cumplimiento de Microsoft 365.
- **Accionable**: proporciona información para habilitar notificaciones de los empleados, investigaciones de datos e investigaciones de los empleados.

## <a name="workflow"></a>Flujo de trabajo

La administración de riesgos de Insiders le ayuda a identificar, investigar y emprender acciones para enfrentar los riesgos internos de la organización. Con las plantillas de directivas centradas, la señalización exhaustiva de las actividades en el servicio de Microsoft 365 y un flujo de trabajo flexible, puede usar información que requiere acción para identificar y resolver rápidamente el comportamiento arriesgado.

La identificación y resolución de actividades de riesgo internas y problemas de cumplimiento de la administración de riesgos de Insider en Microsoft 365 usa el siguiente flujo de trabajo:

![Flujo de trabajo de administración de riesgos de internación](../media/insider-risk-workflow.png)

### <a name="policies"></a>Directivas

Las directivas de administración de riesgos de Insider se crean mediante plantillas predefinidas y condiciones de directivas que definen qué indicadores de riesgo se examinan en las áreas de características de Microsoft 365. Estas condiciones incluyen cómo se usan los indicadores para las alertas, qué usuarios se incluyen en la Directiva, qué servicios se priorizan y el período de tiempo de supervisión.

Puede seleccionar entre las siguientes [plantillas de directiva](insider-risk-management-policies.md#policy-templates) para empezar rápidamente con la administración de riesgos de Insider:

- Robo de datos del empleado
- Pérdidas de datos
- Lenguaje ofensivo en el correo electrónico

Para obtener más información, vea [directivas de administración de riesgos de Insider](insider-risk-management-policies.md).

![Panel de directivas de administración de riesgos de Insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Los indicadores de riesgo generan automáticamente alertas que coinciden con las condiciones de la Directiva y se muestran en el **Panel alertas**. Este panel habilita una vista rápida de todas las alertas que necesitan revisar, abrir alertas a lo largo del tiempo y estadísticas de alertas de la organización. Todas las alertas de Directiva se muestran con información asociada para ayudarle a identificar rápidamente el estado actual de las alertas existentes y nuevas alertas que necesitan acción:

- Estado
- Severity
- Tiempo detectado
- Case
- Estado del caso

Para obtener más información, vea [alertas de administración de riesgos de Insider](insider-risk-management-alerts.md).

![Panel de alertas de administración de riesgos de Insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Prioridades

Las nuevas actividades que necesitan investigación generan automáticamente alertas a las que se asigna un estado de *revisión de necesidades* . Los revisores pueden identificar rápidamente estas alertas y desplazarse por cada una para evaluar y clasificar. 

Las alertas se resuelven abriendo un nuevo caso, asignando la alerta a un caso existente o desechando la alerta. Mediante el uso de filtros de alerta, es fácil identificar rápidamente las alertas por estado, gravedad o tiempo detectado. Como parte del proceso de evaluación de prioridades, los revisores pueden ver los detalles de la alerta para la coincidencia de la Directiva, ver la actividad de usuario asociada a la coincidencia, ver la gravedad de la alerta y revisar la información de Perfil de usuario.

![Clasificación de la administración de riesgos de Insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Averiguar

Los casos se crean para las alertas que requieren una revisión y una investigación más detalladas de los detalles y las circunstancias en las que coincide la Directiva. El **Panel de caso** proporciona una vista general de todos los casos activos, casos abiertos a lo largo del tiempo, y estadísticas de casos para la organización. Los revisores pueden filtrar rápidamente los casos por estado, la fecha en la que se abrió el caso y la fecha en que se actualizó por última vez el caso.

Al seleccionar un caso en el panel del caso, se abre el caso de investigación y revisión. Este paso es el corazón del flujo de trabajo de administración de riesgos de Insider. Esta área es donde los indicadores de actividad de riesgos, las condiciones de las directivas, los detalles de las alertas y los detalles de los empleados se sintetizan en una vista integrada para los revisores. Las principales herramientas de investigación de esta área son:

- **Actividad de usuario**: la actividad de los usuarios se muestra automáticamente en un gráfico interactivo que traza las actividades de riesgo a lo largo del tiempo y por nivel de riesgo para las actividades de riesgo actuales o pasadas. Los revisores pueden filtrar y ver rápidamente todo el historial de riesgos para el empleado y profundizar en actividades específicas para obtener más información.
- **Explorador de contenido**: todos los archivos de datos y mensajes de correo electrónico asociados con actividades de riesgo de alertas se capturan automáticamente y se muestran en el explorador de contenido. Los revisores pueden filtrar y ver los archivos y los mensajes por origen de datos, tipo de archivo, etiquetas, conversación y muchos más atributos.
- **Notas del caso**: los revisores proporcionan notas para un caso en la sección Notas de caso. Esta lista consolida todas las notas en una vista central e incluye la información enviada por el revisor y la fecha.

Para obtener más información, vea [casos de administración de riesgos de Insider](insider-risk-management-cases.md).

![Investigación de administración de riesgos de Insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Action

Una vez que se han investigado los casos, los revisores pueden tomar medidas rápidamente para resolver el caso o colaborar con otras partes interesadas de riesgo de la organización. Cuando los empleados infringen accidental o involuntariamente las condiciones de las directivas, se puede enviar una notificación de recordatorio simple al empleado a partir de plantillas de notificación que puede configurar para su organización. Estos avisos pueden servir como recordatorios sencillos o dirigir al empleado a un entrenamiento o guía de refresco para ayudar a evitar un comportamiento arriesgado futuro. Para obtener más información, consulte [plantillas de aviso de administración de riesgos de Insider](insider-risk-management-notices.md).

En las situaciones más graves, es posible que necesite compartir la información del caso de administración de riesgos de Insider con otros revisores de la organización. La administración de riesgos de Insider se integra estrechamente con otras características de cumplimiento de Microsoft 365 para ayudarle con la resolución de riesgos de un extremo a otro. Escalar un caso para la investigación le permite transferir datos y administrar el caso a la exhibición avanzada de documentos electrónicos en Microsoft 365. EDiscovery avanzado proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. Permite a los equipos legales administrar todo el flujo de trabajo de notificación de retención legal. Para obtener más información sobre los casos avanzados de eDiscovery, vea [información general sobre EDiscovery avanzado en Microsoft 365](overview-ediscovery-20.md).

## <a name="scenarios"></a>Escenarios

La administración de riesgos de Insiders puede ayudarle a detectar, investigar y emprender acciones para mitigar los riesgos internos de su organización en varios escenarios comunes:

### <a name="data-theft-by-departing-employee"></a>Robo de datos al que se parte del empleado

Cuando los empleados dejan una organización, ya sea voluntariamente o como resultado de la terminación, a menudo hay preocupaciones legítimas de que los datos de la empresa, el cliente y los empleados estén en riesgo. Los empleados pueden asumir inocentemente que los datos del proyecto no son propios o pueden sentirse tentados a tomar los datos de la compañía para obtener un beneficio personal y infringir la política de la compañía y los estándares legales. Las directivas de administración de riesgos de Insider que usan la plantilla de directiva de robo de datos del empleado que la [integran](insider-risk-management-policies.md#policy-templates) automáticamente detectan actividades normalmente asociadas con este tipo de robo. Con esta Directiva, recibirá automáticamente alertas para actividades sospechosas asociadas con el robo de empleados, de modo que pueda realizar las acciones de investigación adecuadas. Para esta plantilla de Directiva, se necesita configurar un [conector de Microsoft 365](import-hr-data.md) para la organización.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Pérdida intencional o involuntaria de información confidencial o confidencial

En la mayoría de los casos, los empleados intentan manejar correctamente la información confidencial o confidencial. Pero, en ocasiones, los empleados cometen errores y la información se comparten de forma accidental fuera de su organización o infringen sus directivas de protección de la información. A veces, los empleados pueden perder o compartir intencionadamente información confidencial y confidencial con malas intenciones y para obtener una ganancia personal potencial. Las directivas de administración de riesgos de Insider creadas mediante la plantilla de directiva de [pérdidas de datos](insider-risk-management-policies.md#policy-templates) detectan automáticamente las actividades asociadas normalmente al uso compartido de información confidencial. La configuración de al menos una [Directiva de protección contra la pérdida de datos (DLP)](create-test-tune-dlp-policy.md) de Microsoft 365 para la organización es necesaria para esta plantilla de directiva.

### <a name="actions-and-behaviors-that-violate-corporate-policies"></a>Acciones y comportamientos que infringen las directivas corporativas

Las comunicaciones entre empleados son a menudo una fuente de infracciones accidentales o malintencionadas de las directivas corporativas. Estas infracciones pueden incluir un lenguaje ofensivo, amenazas y el Cyber-acosos entre empleados. Este tipo de actividad contribuye a un entorno de trabajo hostil y puede dar lugar a acciones legales con los empleados y la organización de mayor tamaño. La administración de riesgos de Insiders usa nuevos clasificadores de Microsoft 365 integrados y el [lenguaje ofensivo en la plantilla de directiva de correo electrónico](insider-risk-management-policies.md#policy-templates) . Estos clasificadores y plantillas permiten la configuración rápida de una directiva para detectar automáticamente y alertarle de este tipo de comportamiento.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Consulte [planeación de la administración de riesgos de Insiders](insider-risk-management-plan.md) para obtener más sobre cómo prepararse para habilitar directivas de administración de riesgos de Insider en su organización.
- Consulte Introducción a la [Administración de riesgos de Insider](insider-risk-management-configure.md) para configurar los requisitos previos, crear directivas y empezar a recibir alertas.
