---
title: Notificación de infracciones de datos según el RGPD de Azure y Dynamics 365
description: Le explicamos cómo Azure y Dynamics 365 protege contra una vulneración de datos personales y cómo Microsoft responde y le notifica si se produce una vulneración.
keywords: Azure, Microsoft 365, Dynamics 365, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 7cc809780d57bd3b2bb499dfb05c3f623d158cd6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594440"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Notificación de infracciones de datos según el RGPD de Azure y Dynamics 365

Microsoft Azure toma muy en serio sus obligaciones sobre la normativa general de protección de datos (RGPD). Microsoft Azure toma medidas de seguridad para protegerse de las infracciones de datos, incluyendo controles de seguridad físicos y lógicos, así como automatización los procesos de seguridad, directivas de seguridad y privacidad de la información completas y formación en seguridad y privacidad para todo el personal.

La seguridad se integra en Microsoft Azure desde cero, comenzando con el [Ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/), un proceso de desarrollo obligatorio que incorpora metodologías de privacidad por diseño y privacidad de forma predeterminada. El criterio rector de la estrategia de seguridad de Microsoft es "asumir la infracción" que es una extensión de la estrategia de defensa exhaustiva. Al poner a prueba capacidades de seguridad de Azure constantemente, Microsoft puede mantenerse por delante de las amenazas emergentes. Para obtener más información sobre la seguridad de Azure, revise estos [recursos](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft tiene un servicio de respuesta a incidentes 24/7 global adecuado para reducir los efectos de los ataques contra Microsoft Azure. Acreditado mediante varias auditorías de seguridad y cumplimiento (por ejemplo, [ISO/CEI 27018](offering-iso-27018.md)), Microsoft emplea operaciones y procesos de gran rigor en sus centros de datos para evitar el acceso no autorizado, incluyendo la supervisión en vídeo 24/7, personal de seguridad formado, tarjetas inteligentes y controles biométricos.

## <a name="detection-of-potential-breaches"></a>Detección de posibles vulneraciones

Debido a la naturaleza de la informática en la nube moderna, no todas las infracciones de datos que se producen en un entorno de nube de cliente implican el uso de servicios de Microsoft Azure. Microsoft emplea un modelo de responsabilidad compartido para que los servicios de Azure puedan definir responsabilidades operativas y de seguridad. La responsabilidad compartida es importante en la seguridad de un servicio en la nube, ya que tanto el proveedor de servicios en la nube como el cliente son responsables de distintos aspectos de la seguridad en la nube.

Microsoft no supervisa o responde a los incidentes de seguridad responsabilidad del cliente. Una vulneración del cliente no puede tratarse como incidente de seguridad de Azure y es responsabilidad del inquilino del cliente administrar la respuesta. La respuesta al incidente del cliente puede implicar la colaboración con [atención al cliente](https://azure.microsoft.com/support/options/) de Microsoft Azure, según los contratos de servicio correspondientes. Microsoft Azure también ofrece varios servicios (por ejemplo, [Azure Security Center](https://azure.microsoft.com/services/security-center/)) que los clientes pueden utilizar para desarrollar y administrar la respuesta a incidentes de seguridad.

Azure responde a una posible vulneración de datos según el proceso de respuesta a incidentes de seguridad, un subconjunto del plan de administración de incidentes de Microsoft Azure. La respuesta a incidentes de seguridad de Azure se implementa con un proceso de cinco fases: detección, evaluación, diagnóstico, estabilización y cierre. El equipo de respuesta a incidentes de seguridad puede alternar entre las fases de diagnóstico y estabilización a medida que avanza a la investigación. A continuación se expone información general sobre el proceso de respuesta de seguridad:

|**Fase**|**Descripción**|
| ------- | ------------- |
| ***1: detección*** | Primera indicación de un posible incidente. |
| ***2: evaluación*** | Un miembro del equipo de respuesta ante incidentes evalúa el impacto y la gravedad del evento. Según las pruebas, la evaluación puede o no provocar una escalación al equipo de respuesta de seguridad. |
| ***3: diagnóstico*** | Los expertos en respuestas de seguridad llevan a cabo la investigación técnica o forense, la identificación de estrategias de contención, la mitigación y la aplicación de soluciones alternativas. Si el equipo de seguridad cree que los datos del cliente pueden haberse expuesto a una ejecución individual ilegal o no autorizada, se inicia el proceso de notificación de incidentes del cliente de forma paralela. |
| ***4: estabilización y recuperación*** | El equipo de respuesta ante incidentes crea un plan de recuperación para mitigar el problema. De forma inmediata y en paralelo al diagnóstico, pueden darse pasos de contención de crisis, como poner en cuarentena los sistemas afectados. Pueden planearse mitigaciones a largo plazo después de solucionar el riesgo inmediato. |
| ***5: cierre y análisis posterior*** | El equipo de respuesta ante incidentes crea un análisis posterior que expone los detalles del incidente, con la intención de revisar directivas, procedimientos y procesos para evitar que el evento vuelva a producirse. |

Las notas del producto [Respuesta de seguridad de Microsoft Azure en la nube](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) dan más detalles acerca de cómo Microsoft investiga, administra y responde a los incidentes de seguridad en Azure.

Los procesos de detección usados por Microsoft Azure están diseñados para detectar sobre eventos que ponen en riesgo la integridad, confidencialidad y disponibilidad de los servicios de Azure. Algunas situaciones pueden desencadenar una investigación:

- Alertas automatizadas del sistema mediante marcos internos de monitoreo y alerta. Estas alertas pueden interferir con alarmas basadas en firmas, como antimalware, detección de intrusiones o mediante algoritmos diseñados para identificar actividades previstas y generar alertas ante anomalías.
- Informes internos de los servicios Microsoft ejecutándose en Microsoft Azure y Azure Government.
- Las vulnerabilidades de seguridad se notifican al [Centro de respuestas de seguridad de Microsoft (MSRC)](https://technet.microsoft.com/security/dn440717) en la dirección [secure@microsoft.com](mailto:secure@microsoft.com). El MSRC trabaja con socios e investigadores de seguridad de todo el mundo para evitar incidentes de seguridad y mejorar la seguridad de los productos de Microsoft.
- Los informes de cliente a través del [Portal de soporte técnico al cliente](https://www.windowsazure.com/support/contact/) o el portal de administración de Microsoft Azure y Azure Government, que describen la actividad sospechosa atribuida a la infraestructura de Azure (en lugar de la actividad que se producen en el ámbito de responsabilidad del cliente).
- Actividad de los [equipos de seguridad rojo y azul](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Esta estrategia usa un equipo Rojo de expertos altamente cualificados en seguridad ofensiva de Microsoft para descubrir y atacar debilidades potenciales en los servicios de Azure. El equipo Azul de respuesta de seguridad debe detectar la actividad del equipo rojo y defenderse contra ella. Las acciones de los equipos Rojo y Azul se usan para comprobar que los esfuerzos de respuesta de seguridad de Azure son efectivos a la hora de administrar incidentes de seguridad. Las actividades de los equipos de seguridad Rojo y Azul se basan en las reglas de compromiso para garantizar la protección de los datos de clientes.
- Remisiones a una instancia superior por parte de los operadores de servicios de Azure. Los empleados de Microsoft están preparados para identificar y escalar los posibles problemas de seguridad.

## <a name="azures-data-breach-response"></a>Respuesta de infracción de datos de Azure

Microsoft asigna los niveles de prioridad y gravedad adecuados investigando el impacto funcional, la capacidad de recuperación y el impacto de la información del incidente. Tanto la prioridad como la gravedad pueden cambiar a lo largo de la investigación, en función de nuevos resultados y conclusiones. Los eventos de seguridad que impliquen un riesgo inminente o confirmado para los datos de los clientes se tratan como muy graves y se trabaja de forma urgente para su resolución. 

Microsoft Azure clasifica el impacto del incidente en la información en las siguientes categorías de infracciones:

| **Categoría**             | **Definición**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Ninguna***               | No se ha extraído, cambiado, eliminado o comprometido ninguna información.                                                      |
| ***Infracción de privacidad***     | Se ha comprometido o accedido a datos personales confidenciales de contribuyentes, empleados, beneficiarios, etc.                                |
| ***Infracción de propietario*** | Se ha comprometido o accedido a información del propietario sin clasificar, como información de infraestructura crítica protegida (PCII).  |
| ***Pérdida de integridad***     | Se ha modificado o eliminado información confidencial o de propiedad.                                                                     |

El equipo de respuesta de seguridad trabaja con los ingenieros de seguridad de Microsoft Azure y PYME para clasificar el evento con datos reales de las pruebas. Un evento de seguridad se puede clasificar como:

- **Falso positivo**: un evento que cumple con los criterios de detección pero que se considera parte de una práctica comercial normal y es preciso que sea filtrado. El equipo de servicio identifica la causa principal de los falsos positivos y los soluciona de forma sistemática aprovechando los orígenes de detección, y ajustándolos según sea necesario.
- **Incidente de seguridad**: un incidente en el que se produce un acceso ilegal a los datos de los clientes o de soporte técnico almacenados en equipos o instalaciones de Microsoft; o un acceso no autorizado a dichos equipos o instalaciones que da como resultado la pérdida, divulgación o modificación de datos de clientes o de soporte técnico.
- **Incidente de seguridad o privacidad denunciado por el cliente**: un acceso o un uso ilegal o no autorizado de sistemas, equipos o instalaciones de Microsoft que da como resultado la divulgación, modificación o pérdida de datos de clientes.
- **Infracción de privacidad**: caso específico de un incidente relativo a la seguridad que involucra datos personales. Los procedimientos de control son los mismos que los de un incidente de seguridad.

Para que se declare una CRSPI, Microsoft debe determinar que el acceso no autorizado a los datos del cliente se ha producido, o es probable que lo haya hecho, o existe un compromiso legal o contractual que fuerce la notificación. Es preferible, aunque no necesario, que se conozcan los pasos de impacto, acceso a los recursos y pasos de reparación del cliente específico. Un incidente se declara, en general, como CRSPI después de la conclusión de la fase de diagnóstico de un incidente de seguridad. Sin embargo, la declaración puede producirse en cualquier momento en el que esté disponible toda la información pertinente. El administrador del incidente de seguridad debe establecer pruebas más allá de la duda razonable de que se ha producido un evento del que informar para iniciar la ejecución del Proceso de notificación de incidentes del cliente.

Durante la investigación, el equipo de respuesta de seguridad trabaja junto a asistentes legales de todo el mundo para ayudar a garantizar que los análisis se realizan siguiendo los compromisos y las obligaciones legales con los clientes. También hay importantes restricciones sobre el visionado de datos de clientes y sistemas, además de sobre su manejo en varios entornos operativos. Los datos confidenciales y de los clientes no se transfieren fuera del entorno de producción sin la aprobación escrita del administrador de incidentes registrada en el tique de incidente correspondiente.

Microsoft comprueba que el riesgo para los clientes y negocios se ha contenido con éxito y que las medidas correctivas se han implementado. En caso necesario, se llevan a cabo pasos de atenuación de emergencia para resolver los riesgos de seguridad inmediatos asociados con el evento.

Microsoft también realiza un análisis final interno para las vulneraciones de datos. Como parte de este ejercicio, se evalúan los procedimientos operativos y la suficiencia de respuesta y se identifican e implementan las actualizaciones necesarias para la respuesta ante incidentes de seguridad o procesos relacionados. Los análisis finales internos para las vulneraciones de datos son registros muy confidenciales no disponibles para los clientes. Los análisis finales pueden, sin embargo, resumirse e incluirse en otras notificaciones de eventos del cliente. Estos informes se proporcionan a auditores externos para su revisión como parte del ciclo de auditoría rutinario de Azure.

## <a name="customer-notification"></a>Notificación al cliente

Microsoft Azure notifica a clientes y organismos reguladores acerca de las vulneraciones de datos según sea necesario. Microsoft depende de una gran compartimentación interna en la operación de Azure. También son sólidos los registros de flujo de datos. Una ventaja de este diseño es que la mayoría de incidentes pueden rastrearse hasta clientes específicos. El objetivo es proporcionar a los clientes afectados con un aviso preciso, puntual y efectivo cuando han sufrido una vulneración de datos.

Tras la declaración de un CRSPI, el proceso de notificación tiene lugar tan pronto como sea posible, pero hay que considerar los riesgos de seguridad de actuar demasiado rápido. Por lo general, se comienza a redactar las notificaciones durante la investigación de la incidencia. Los avisos a los clientes se entregan en no más de 72 horas desde el momento en que se declaró una vulneración, *excepto* en las siguientes circunstancias:

- Microsoft cree que el acto de realizar una notificación aumentará el riesgo para otros clientes. Por ejemplo, la notificación puede alertar a un adversario y provocar una incapacidad para poner remedio.
- Otras circunstancias inusuales o extremas expuestas por el departamento legal de Microsoft, asuntos legales y externos corporativos (CELA), y el administrador de incidentes ejecutivo.
- El plazo de 72 horas puede permitir que algunos detalles del incidente estén disponibles. Estos se proporcionan a los clientes y a las autoridades de reglamentación mientras avanza la investigación.

Microsoft Azure proporciona a los clientes información detallada, lo que les permite realizar investigaciones internas y ayudar a cumplir los compromisos de usuario final, mientras no retrase indebidamente el proceso de notificación.

La notificación de una vulneración de datos personales se entregará al cliente por cualquier medio elegido por Microsoft, incluyendo el correo electrónico. La notificación de una vulneración de datos se enviará a la lista de contactos de seguridad proporcionada en Azure Security Center, que puede configurarse siguiendo las [directrices de implementación](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Si no se proporciona información de contacto en el centro de seguridad de Azure, la notificación se envía a uno o varios administradores de una suscripción de Azure. Para asegurarse de que pueda entregarse la notificación correctamente, es responsabilidad del cliente proporcionar información de contacto administrativa correcta en cada suscripción y portal de servicios en línea aplicables.

El grupo de Microsoft Azure o Azure Government también puede notificar al personal adicional de Microsoft, como el servicio de atención al cliente (CSS), el administrador de cuentas del cliente (o) o el administrador de cuentas técnicas (TAM). Por lo general, estas personas suelen tener relaciones estrechas con el cliente y pueden facilitar la reparación más rápida

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Características de seguridad integradas en Microsoft Dynamics 365

Microsoft Dynamics 365 usa la infraestructura de servicios en la nube y las características de seguridad integradas para garantizar la integridad de los datos con medidas de seguridad y mecanismos de protección. Además, Dynamics 365 ofrece acceso a datos y colaboración eficientes con integridad de los datos y privacidad en las áreas siguientes: [identidad segura, protección de datos, seguridad basada en roles y administración de amenazas](https://www.microsoft.com/trustcenter/security/dynamics365-security).

La oferta de Microsoft Dynamics 365 sigue las mismas medidas técnicas y de organización que los equipos del servicio de Microsoft Azure llevan a cabo para proteger contra posibles vulneración de datos. Por tanto, cualquier información registrada en el documento de notificación "Vulneración de datos de Microsoft Azure" es en este caso también aplicable al servicio de Microsoft Dynamics 365.

## <a name="learn-more"></a>Más información

[Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
