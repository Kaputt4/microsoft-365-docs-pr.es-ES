---
title: Cumplimiento de las comunicaciones
description: Obtenga información sobre el cumplimiento de la comunicación en Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 71226634f17e8e801c409e513494dfdcc19d0719
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046298"
---
# <a name="communication-compliance-in-microsoft-365"></a>Cumplimiento de la comunicación en Microsoft 365

El cumplimiento de la comunicación forma parte de la nueva solución de riesgo de Insider que se establece en Microsoft 365, que ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y realizar acciones de corrección para los mensajes inapropiados de la organización. Las directivas predefinidas y personalizadas le permiten analizar las comunicaciones internas y externas de las coincidencias de directivas para que puedan examinarlas los revisores designados. Los revisores pueden investigar el correo electrónico explorado, Microsoft Teams, Yammer o las comunicaciones de terceros de la organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen con los estándares de mensajes de la organización.

Las directivas de cumplimiento de comunicaciones de Microsoft 365 ayudan a superar muchos de los retos modernos asociados con el cumplimiento y las comunicaciones internas y externas, entre los que se incluyen:

- Análisis de tipos crecientes de canales de comunicación
- El volumen creciente de los datos de los mensajes
- Cumplimiento normativo y riesgo de multas

En algunas organizaciones, puede haber una separación de tareas entre el soporte de ti y el grupo de administración de cumplimiento. Microsoft 365 admite la separación entre la configuración de cumplimiento de la comunicación y la configuración de directivas para el análisis de comunicaciones. Por ejemplo, el grupo de TI de una organización puede ser responsable de configurar los permisos de funciones y grupos para que admitan las directivas de cumplimiento de comunicaciones configuradas y administradas por el equipo de cumplimiento de la organización.

Para obtener una introducción rápida al cumplimiento de las normas de comunicación, consulte el vídeo " [detectar el acoso del lugar de trabajo y responder con el cumplimiento de la comunicación" en microsoft 365](https://youtu.be/z33ji7a7Zho) en el canal de [Microsoft](https://www.youtube.com/user/OfficeGarageSeries).

## <a name="scenarios-for-communication-compliance"></a>Escenarios para el cumplimiento de la comunicación

Las directivas de cumplimiento de comunicaciones pueden ayudarle a revisar los mensajes de su organización en varias áreas de cumplimiento importantes:

- **Directivas corporativas**

    Los empleados deben cumplir con el uso aceptable, los estándares éticos y otras directivas corporativas en todas sus comunicaciones relacionadas con la empresa. Las directivas de cumplimiento de comunicaciones pueden detectar coincidencias de directivas y ayudarle a tomar medidas correctivas para ayudar a mitigar estos tipos de incidentes. Por ejemplo, puede analizar las comunicaciones de los empleados de su organización para detectar posibles problemas de recursos humanos, como acoso o el uso de lenguaje inadecuado o ofensivo.

- **Administración de riesgos**

    Las organizaciones son responsables de todas las comunicaciones distribuidas en su infraestructura y en los sistemas de la red corporativa. El uso de directivas de supervisión de comunicaciones para ayudar a identificar y administrar posibles exposiciones y riesgos legales puede ayudar a minimizar los riesgos antes de que puedan dañar las operaciones corporativas. Por ejemplo, puede analizar los mensajes de su organización en busca de comunicaciones no autorizadas sobre proyectos confidenciales, como próximas adquisiciones, fusiones, divulgaciones de ingresos, reorganizaciones o cambios de equipo de liderazgo.

- **Cumplimiento normativo**

    La mayoría de las organizaciones deben cumplir con algún tipo de estándares de cumplimiento normativo como parte de los procedimientos de funcionamiento normales. Estas normativas a menudo requieren que las organizaciones implementen algún tipo de supervisión o proceso de supervisión para la mensajería que sea adecuada para su sector. La regla 3110 de la autoridad reguladora del sector financiero (FINRA) es un buen ejemplo de un requisito para que las organizaciones dispongan de procedimientos de supervisión para analizar las comunicaciones de los empleados y los tipos de empresas en las que participa. Otro ejemplo podría ser la necesidad de revisar las comunicaciones de agentes en su organización para protegerse contra el blanqueo de dinero, la colusión o las actividades de soborno. Las directivas de cumplimiento de comunicaciones pueden ayudar a su organización a cumplir estos requisitos proporcionando un proceso para analizar e informar sobre comunicaciones corporativas. Para obtener más información sobre la compatibilidad con organizaciones financieras, consulte [key Compliance and Security Considerations for US bancaria and Capital Markets](../solutions/financial-services-secure-collaboration.md).

## <a name="new-enhancements"></a>Nuevas mejoras

El cumplimiento de la comunicación en Microsoft 365 se basa en las características de las [directivas de supervisión en Office 365](supervision-policies.md) con varias mejoras nuevas:

- Plantillas inteligentes y personalizables
- Flujos de trabajo de corrección flexibles
- Información que requiere acción

![Página principal de cumplimiento de comunicaciones](../media/communication-compliance-home.png)

### <a name="intelligent-customizable-templates"></a>Plantillas inteligentes y personalizables

Las plantillas inteligentes y personalizables en el cumplimiento de la comunicación le permiten aplicar el aprendizaje automático para detectar de manera inteligente las violaciones de comunicación en su organización.

- **Plantillas preconfiguradas personalizables**: las nuevas plantillas de directiva ayudan a abordar los riesgos de comunicaciones más comunes. La creación de directivas iniciales y la actualización de seguimiento ahora son más rápidas con un Antiacoso predefinido y un lenguaje ofensivo, información confidencial y plantillas de cumplimiento normativo.
- **Compatibilidad con nuevos equipos de aprendizaje**: los [clasificadores](classifier-getting-started-with.md) de amenazas, acosos y blasfemias integrados ayudan a reducir los falsos positivos en los mensajes examinados, lo que ahorra tiempo a los revisores durante el proceso de investigación y corrección.
- **Generador de condiciones mejorado**: la configuración de las condiciones de la Directiva ahora se simplifica en una sola experiencia integrada en el Asistente para directivas, lo que reduce la confusión en el modo en que se aplican las directivas.

### <a name="flexible-remediation-workflows"></a>Flujos de trabajo de corrección flexibles

Los flujos de trabajo de corrección integrados permiten identificar rápidamente y realizar acciones en mensajes con coincidencias de directivas en la organización. Las siguientes características nuevas aumentan la eficiencia para las actividades de investigación y corrección:

- **Flujo de trabajo de corrección flexible**: el nuevo flujo de trabajo de corrección ayuda a tomar medidas rápidamente sobre las coincidencias de las directivas, incluidas las nuevas opciones para remitir mensajes a otros revisores y enviar notificaciones por correo electrónico a los usuarios con coincidencias de directivas.
- **Subprocesamiento de conversación**: los mensajes ahora están agrupados visualmente por mensaje original y todos los mensajes de respuesta asociados, lo que le da un mejor contexto durante la investigación y las acciones de corrección.
- **Resaltado de palabras clave**: las condiciones de la Directiva de coincidencia de términos se resaltan en la vista texto del mensaje para ayudar a los revisores a localizar y corregir las alertas de directiva rápidamente.
- **Detección de duplicados exactos y Near**: además de analizar los términos exactos que coinciden con las directivas de cumplimiento de comunicación, Near duplicados los grupos de términos y mensajes que se asemejan de forma textual y que ayudan a acelerar el proceso de revisión.
- **Nuevos filtros**: Investigue y solucione las alertas de directiva más rápidamente con filtros de mensaje para varios campos, incluidos el remitente, el destinatario, la fecha, los dominios y muchos más.
- **Vistas de mensajes mejoradas**: las acciones de investigación y corrección ahora son más rápidas con las vistas de nuevos orígenes de mensajes, texto y anotaciones. Los datos adjuntos de mensajes ahora se pueden ver para proporcionar contexto completo cuando se toman acciones de corrección.
- **Vista historial de usuarios**: vista histórica de todas las actividades de corrección de mensajes de usuario, como las notificaciones pasadas y las escalaciones de las coincidencias de directivas, ahora proporciona revisores con más contexto durante el proceso de flujo de trabajo de corrección. Las instancias de la primera vez o de repetición de las coincidencias de directivas para los usuarios ahora se archivan y se pueden ver fácilmente.

### <a name="actionable-insights"></a>Información que requiere acción

Los nuevos paneles interactivos para alertas, coincidencias de directivas, acciones y tendencias le ayudan a ver rápidamente el estado de las alertas pendientes y resueltas en su organización.

- **Alertas inteligentes proactivas**: las alertas de las coincidencias de directivas que requieren atención inmediata incluyen nuevos paneles para los elementos pendientes ordenados por gravedad y nuevas notificaciones de correo electrónico automáticas enviadas a los revisores designados.
- **Paneles interactivos**: los nuevos paneles muestran coincidencias de directivas, acciones pendientes y resueltas, y tendencias de los usuarios y la Directiva.
- **Compatibilidad con la auditoría**: un registro completo de las actividades de la Directiva y la revisión se exporta fácilmente desde el centro de cumplimiento de Microsoft 365 para ayudar a admitir solicitudes de revisión de auditoría.

## <a name="integration-with-microsoft-365-services"></a>Integración con los servicios de Microsoft 365

Las directivas de cumplimiento de comunicaciones examinan y capturan mensajes en varios canales de comunicación para ayudarle a revisar y corregir rápidamente los problemas de cumplimiento:

- **Microsoft Teams**: las comunicaciones de chat para canales públicos y privados de [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) y chats individuales se admiten en el cumplimiento de la comunicación como origen de canal independiente o con otros servicios de Microsoft 365. Las directivas ahora analizan automáticamente todos los canales y equipos de Microsoft Teams para determinados usuarios definidos en una directiva, lo que elimina la necesidad de mantener una lista de asignación independiente para las asignaciones de Microsoft Teams.
- **Exchange Online**: todos los buzones hospedados en [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) en su organización de 365 de Microsoft tienen derecho a análisis. Los correos electrónicos y datos adjuntos que cumplen las condiciones de la Directiva de cumplimiento están disponibles instantáneamente para la supervisión y en los informes de supervisión. Exchange Online es ahora un canal de origen opcional y ya no es necesario en las directivas de cumplimiento de comunicaciones.
- **Yammer**: los mensajes privados y las conversaciones de la comunidad pública en [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page) se admiten en las directivas de cumplimiento de comunicaciones. Yammer es un canal opcional y debe estar en [modo nativo](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) para admitir el examen de mensajes y datos adjuntos.
- **Skype empresarial online**: las directivas de cumplimiento de comunicaciones admiten el análisis de comunicaciones de chat y los datos adjuntos asociados en [Skype empresarial online](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online).
- **Orígenes de terceros**: puede examinar mensajes de orígenes de [terceros](archiving-third-party-data.md) para los datos importados en buzones de la organización de Microsoft 365. El cumplimiento de la comunicación admite conexiones a varias plataformas populares, entre las que se incluyen los Bloomberg, Facebook, Twitter y otros usuarios instantáneos.

Para obtener más información acerca de la compatibilidad del canal de mensajería en las directivas de cumplimiento de comunicaciones, consulte [tipos de comunicación admitidos](communication-compliance-feature-reference.md#supported-communication-types).

## <a name="workflow"></a>Flujo de trabajo

El cumplimiento de la comunicación le ayuda a enfrentar Pain Points comunes asociados con el cumplimiento de las directivas internas y los requisitos de cumplimiento normativo. Con las plantillas de directivas centradas y un flujo de trabajo flexible, puede usar la información que requiere acción para resolver rápidamente problemas de cumplimiento detectados.

La identificación y resolución de problemas de cumplimiento con el cumplimiento de la comunicación en Microsoft 365 usa el siguiente flujo de trabajo:

![Flujo de trabajo de cumplimiento de comunicaciones](../media/communication-compliance-workflow.png)

### <a name="configure"></a>Configurar

En este paso del flujo de trabajo, se identifican los requisitos de cumplimiento y se configuran las directivas de cumplimiento de comunicaciones aplicables. Las plantillas de Directiva son una forma excelente de configurar rápidamente una nueva Directiva de cumplimiento, pero también modificar y actualizar rápidamente las directivas a medida que cambian sus requisitos. Por ejemplo, es posible que desee probar rápidamente una directiva en busca de lenguaje ofensivo y Antiacoso en las comunicaciones de un pequeño grupo de usuarios antes de configurar una directiva para todos los usuarios de la organización.

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de comunicaciones. Para habilitar los permisos para las características de cumplimiento de comunicaciones, consulte [hacer que el cumplimiento de la comunicación esté disponible en su organización](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance).

Puede elegir entre las siguientes plantillas de directiva en el centro de cumplimiento de Microsoft 365:

- **Idioma ofensivo y Antiacoso**: Use esta plantilla para crear rápidamente una directiva que use el clasificador integrado para detectar automáticamente el contenido que pueda considerarse ofensivo o ofensivo.
- **Información confidencial**: Use esta plantilla para crear una directiva para examinar las comunicaciones que contienen tipos de información confidencial o palabras clave definidas para ayudar a garantizar que no se compartan datos importantes con personas que no tienen acceso.
- **Cumplimiento de normativas**: Use esta plantilla para crear una directiva para analizar las comunicaciones en busca de referencias a términos financieros estándar asociados con los estándares normativos.
- **Directiva personalizada**: Use esta plantilla para configurar canales de comunicación específicos, condiciones de detección individuales y la cantidad de contenido que se va a revisar para la supervisión de la organización.

### <a name="investigate"></a>Averiguar

En este paso, se analizan más detalladamente los problemas detectados como coincidencia con las directivas de cumplimiento de comunicaciones. Este paso incluye las siguientes acciones disponibles en el centro de cumplimiento de Microsoft 365:

- **Alertas**: cuando un mensaje coincide con una directiva de supervisión, se genera automáticamente una alerta. Para cada alerta, puede ver el estado, la gravedad, el tiempo detectado y, si se asigna un caso y su estado. Las nuevas alertas se muestran en la Página principal de cumplimiento de comunicaciones y en la página **alertas** y aparecen en orden de gravedad.
- **Administración de problemas**: para cada alerta, puede emprender acciones de investigación para ayudar a corregir el problema detectado en el mensaje.
- **Revisión del documento**: durante la investigación de un problema, puede usar varias vistas del mensaje para evaluar correctamente el problema detectado. Las vistas incluyen una vista de Resumen de conversación, de sólo texto, anotada y detallada de la conversación de comunicación.
- **Revisión del historial de actividad**de los usuarios: ver el historial de las actividades de los mensajes de usuario y las acciones de corrección, como las notificaciones y las escalaciones pasadas, para las coincidencias de directivas.
- **Filters**: Use filtros como Sender, recipient, Date y sujeto para restringir rápidamente las alertas de mensaje que desea revisar.

### <a name="remediate"></a>Corrección

El siguiente paso consiste en corregir los problemas de cumplimiento de comunicaciones que ha investigado con las siguientes opciones:

- **Resolver**: después de revisar un problema, puede solucionarlo si resuelve la alerta. La resolución de una alerta la elimina de la cola de alertas pendientes y la acción se conserva como una entrada en la cola resuelta para la Directiva de coincidencia. Las alertas se resuelven automáticamente después de marcar la alerta como falso positivo, enviar un aviso a un empleado sobre la alerta o abrir un nuevo caso para la alerta.
- **Etiquete un mensaje**: como parte de la resolución de un problema, puede etiquetar el mensaje detectado como conforme, no compatible o tan dudoso como se relacione con las directivas y los estándares de su organización. El etiquetado puede ayudarle a microfiltrar las alertas de las directivas para las escalaciones o como parte de otros procesos internos de revisión.
- **Notificar al usuario**: a menudo, los usuarios infringen accidental o involuntariamente una directiva de cumplimiento de la comunicación. Puede usar la función Notify para proporcionar un aviso de advertencia al usuario y para resolver el problema.
- **Remitir a otro revisor**: a veces, el revisor inicial de un problema necesita información de otros revisores para ayudar a resolver el incidente. Puede remitir fácilmente los problemas de los mensajes a los revisores de otras áreas de la organización como parte del proceso de resolución.
- **Marcar como falso positivo**: los mensajes que se detectan incorrectamente como coincidencias de las directivas de cumplimiento se aplicarán en ocasiones al proceso de revisión. Puede marcar estos tipos de alertas como falsos positivos y resolver el problema automáticamente.
- **Crear un caso**: en las situaciones más graves, es posible que necesite compartir la información de cumplimiento de comunicaciones con otros revisores de la organización. El cumplimiento de la comunicación se integra estrechamente con otras características de cumplimiento de Microsoft 365 para ayudarle con la resolución de riesgos de un extremo a otro. Escalar un caso para la investigación le permite transferir datos y administrar el caso a la exhibición avanzada de documentos electrónicos en Microsoft 365. EDiscovery avanzado proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. Permite a los equipos legales administrar todo el flujo de trabajo de notificación de retención legal. Para obtener más información sobre los casos avanzados de eDiscovery, vea [información general sobre EDiscovery avanzado en Microsoft 365](overview-ediscovery-20.md).

### <a name="monitor"></a>Supervisar

Mantener el seguimiento y administrar los problemas de cumplimiento identificados por las directivas de cumplimiento de la comunicación abarca todo el proceso de flujo de trabajo. A medida que se generan las alertas y se implementan las acciones de investigación y corrección, es posible que las directivas existentes necesiten revisión y actualizaciones, y que sea necesario crear nuevas directivas.

- **Monitor y informe**: Use los paneles de cumplimiento de comunicaciones, informes, registros de exportación y eventos registrados en los registros de auditoría unificados para evaluar y mejorar continuamente su postura de cumplimiento.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- Para obtener información de planeación, vea [Plan for Communication Compliance](communication-compliance-plan.md).
- Consulte el [caso práctico de Contoso](communication-compliance-case-study.md) y la manera en que configuró rápidamente una directiva de cumplimiento de la comunicación para supervisar el idioma ofensivo en Microsoft Teams, Exchange Online y Yammer Communications.
- Para configurar el cumplimiento de comunicaciones para la organización de Microsoft 365, vea [Configure Communication Compliance for Microsoft 365](communication-compliance-configure.md).
