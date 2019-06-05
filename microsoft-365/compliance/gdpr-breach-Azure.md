---
title: Azure y notificación de infracciones de datos según el RGPD
description: Se explica cómo Azure protege contra una vulneración de datos personales y cómo responde Microsoft y le notifica si se produce una vulneración.
keywords: Azure, Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 7e614554f73f154828536cb4064a5dcf9ec23c26
ms.sourcegitcommit: 6e2a54ec395eaef4c4658ca52322c3d0f184ca02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34698332"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a>Azure y notificación de infracciones de datos según el RGPD

Microsoft Azure toma muy en serio sus obligaciones sobre la normativa general de protección de datos (RGPD). Microsoft Azure toma medidas de seguridad para protegerse de las infracciones de datos, incluyendo controles de seguridad físicos y lógicos, así como automatización los procesos de seguridad, directivas de seguridad y privacidad de la información completas y formación en seguridad y privacidad para todo el personal.

La seguridad se integra en Microsoft Azure desde cero, comenzando con el [Ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/), un proceso de desarrollo obligatorio que incorpora metodologías de privacidad por diseño y privacidad de forma predeterminada. El criterio rector de la estrategia de seguridad de Microsoft es "asumir la infracción" que es una extensión de la estrategia de defensa exhaustiva. Al poner a prueba capacidades de seguridad de Azure constantemente, Microsoft puede mantenerse por delante de las amenazas emergentes. Para obtener más información sobre la seguridad de Azure, revise estos [recursos](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft tiene un servicio de respuesta a incidentes 24/7 global adecuado para reducir los efectos de los ataques contra Microsoft Azure. Acreditado mediante varias auditorías de seguridad y cumplimiento (por ejemplo, [ISO/CEI 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)), Microsoft emplea operaciones y procesos de gran rigor en sus centros de datos para evitar el acceso no autorizado, incluyendo la supervisión en vídeo 24/7, personal de seguridad formado, tarjetas inteligentes y controles biométricos.

## <a name="detection-of-potential-breaches"></a>Detección de posibles vulneraciones

Debido a la naturaleza de la nube moderna, no todas las infracciones de datos que se dan en el entorno de la nube del cliente tienen que ver con los servicios de Microsoft Azure. Microsoft utiliza un modelo de responsabilidad compartida para los servicios de Azure para definir las responsabilidades operativas y de seguridad. La responsabilidad compartida es especialmente importante al tratar la seguridad de un servicio de nube porque tanto el proveedor de servicios y el cliente son responsables de partes de la seguridad en la nube.

Microsoft no supervisa o responde a los incidentes de seguridad responsabilidad del cliente. Una vulneración del cliente no puede tratarse como incidente de seguridad de Azure y es responsabilidad del inquilino del cliente administrar la respuesta. La respuesta al incidente del cliente puede implicar la colaboración con [atención al cliente](https://azure.microsoft.com/support/options/) de Microsoft Azure, según los contratos de servicio correspondientes. Microsoft Azure también ofrece varios servicios (por ejemplo, [Azure Security Center](https://azure.microsoft.com/services/security-center/)) que los clientes pueden utilizar para desarrollar y administrar la respuesta a incidentes de seguridad.

Azure responde a una posible vulneración de datos según el proceso de respuesta a incidentes de seguridad, un subconjunto del plan de administración de incidentes de Microsoft Azure. La respuesta a incidentes de seguridad de Azure se implementa con un proceso de cinco fases: detección, evaluación, diagnóstico, estabilización y cierre. El equipo de respuesta a incidentes de seguridad puede alternar entre las fases de diagnóstico y estabilización a medida que avanza a la investigación. A continuación se expone información general sobre el proceso de respuesta de seguridad:

|**Fase**|**Descripción**|
|:-----|:-----|
| ***1: detección*** | Primera indicación de un posible incidente. |
| ***2: evaluación*** | Un miembro del equipo de respuesta ante incidentes evalúa el impacto y la gravedad del evento. Según las pruebas, la evaluación puede o no provocar una escalación al equipo de respuesta de seguridad. |
| ***3: diagnóstico*** | Los expertos en respuestas de seguridad llevan a cabo la investigación técnica o forense, la identificación de estrategias de contención, la mitigación y la aplicación de soluciones alternativas. Si el equipo de seguridad cree que los datos del cliente pueden haberse expuesto a una ejecución individual ilegal o no autorizada, se inicia el proceso de notificación de incidentes del cliente de forma paralela.|
| ***4: estabilización y recuperación*** | El equipo de respuesta ante incidentes crea un plan de recuperación para mitigar el problema. De forma inmediata y en paralelo al diagnóstico, pueden darse pasos de contención de crisis, como poner en cuarentena los sistemas afectados. Pueden planearse mitigaciones a largo plazo después de solucionar el riesgo inmediato. |
| ***5: cierre y análisis posterior*** | El equipo de respuesta ante incidentes crea un análisis posterior que expone los detalles del incidente, con la intención de revisar directivas, procedimientos y procesos para evitar que el evento vuelva a producirse. |

Las notas del producto [Respuesta de seguridad de Microsoft Azure en la nube](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) dan más detalles acerca de cómo Microsoft investiga, administra y responde a los incidentes de seguridad en Azure.

Los procesos de detección usados por Microsoft Azure están diseñados para detectar sobre eventos que ponen en riesgo la integridad, confidencialidad y disponibilidad de los servicios de Azure. Algunas situaciones pueden desencadenar una investigación:

- Alertas automatizadas del sistema mediante marcos internos de monitoreo y alerta. Estas alertas pueden interferir con alarmas basadas en firmas, como antimalware, detección de intrusiones o mediante algoritmos diseñados para identificar actividades previstas y generar alertas ante anomalías.
- Informes internos de los servicios Microsoft ejecutándose en Microsoft Azure y Azure Government.
- Las vulnerabilidades de seguridad se notifican al [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) a través de <secure@microsoft.com>. El MSRC trabaja con socios e investigadores de seguridad de todo el mundo para ayudar a evitar incidentes de seguridad y para mejorar la seguridad de los productos de Microsoft.
- Los informes de cliente a través del [Portal de soporte técnico al cliente](http://www.windowsazure.com/support/contact/) o el portal de administración de Microsoft Azure y Azure Government, que describen la actividad sospechosa atribuida a la infraestructura de Azure (en lugar de la actividad que se producen en el ámbito de responsabilidad del cliente).
- Actividad [equipo rojo y equipo de azul](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) de seguridad. Esta estrategia usa un equipo rojo de expertos en seguridad ofensiva de Microsoft para detectar y atacar debilidades potenciales en Azure. El equipo azul de respuesta de seguridad debe detectar y defenderse contra la actividad del equipo rojo. Las acciones de ambos equipos se utilizan para verificar que los esfuerzos de respuesta de seguridad de Azure son efectivos a la hora de administrar incidentes de seguridad. Las actividades de los equipos rojo y azul de seguridad operan según las reglas de contratación para ayudar a asegurar la protección de datos de clientes.

-   Escalado por parte de operadores de servicios de Azure. Los empleados de Microsoft están preparados para identificar y escalar los posibles problemas de seguridad.

## <a name="azures-data-breach-response"></a>Respuesta de infracción de datos de Azure

Microsoft asigna la prioridad y los niveles de gravedad adecuados a la investigación al determinar el impacto funcional, la recuperación y el impacto de la información del incidente. Tanto la prioridad como la gravedad pueden cambiar a lo largo de la investigación en función de las conclusiones y de nuevos conocimientos. Los eventos de seguridad que implican riesgo inminente o confirmado a los datos se tratan como graves y se trabaja en ellos de forma ininterrumpida para resolverlos. Microsoft Azure clasifica el impacto de la información del incidente en las siguientes categorías de vulneración:

|**Categoría**|**Definición**|
|:-----|:-----|
| ***Ninguna*** | No se ha extraído, cambiado, eliminado o comprometido ninguna información. |
| ***Infracción de privacidad*** | Se ha comprometido o accedido a datos personales confidenciales de contribuyentes, empleados, beneficiarios, etc. |
| ***Infracción de propietario*** | Se ha comprometido o accedido a información del propietario sin clasificar, como información de infraestructura crítica protegida (PCII).  |
| ***Pérdida de integridad*** | Se ha modificado o eliminado información confidencial o de propiedad. |

El equipo de respuesta de seguridad trabaja con los ingenieros de seguridad de Microsoft Azure y PYME para clasificar el evento con datos reales de las pruebas. Un evento de seguridad se puede clasificar como:

- **Falso positivo:** un evento que cumple los criterios de detección, pero es parte de un procedimiento normal del negocio y es preciso filtrarlo. El equipo de servicio identificar la causa de los falsos positivos y los soluciona de forma sistemática con ajustando los orígenes<span id="_Toc350859432" class="anchor"></span> de detección según sea necesario.
- **Incidente de seguridad:** un incidente en la que se ha producido un acceso ilegal a los datos de los clientes o de soporte técnico almacenados en equipo o instalaciones de Microsoft; o un acceso no autorizado a dicho equipo o instalaciones que ha resultado en la pérdida, divulgación o alteración de datos de clientes o soporte técnico.
- **Incidente de seguridad de los clientes (CRSI):** un acceso o uso ilegal o no autorizado a sistemas, equipo o instalaciones de Microsoft que resulta en la divulgación, modificación o pérdida de datos de clientes.
- **Vulneración de privacidad:** un subtipo de incidente de seguridad relacionado con datos personales. Los procedimientos de control no son diferentes de un incidente de seguridad.

Para que se declare una CRSI, Microsoft debe determinar que el acceso no autorizado a los datos del cliente se ha producido, o es probable que lo haya hecho, o existe un compromiso legal o contractual que fuerce la notificación. Es preferible, aunque no necesario, que se conozcan los pasos de impacto, acceso a los recursos y pasos de reparación del cliente específico. Un incidente se declara, en general, como CRSI después de la conclusión de la fase de diagnóstico de un incidente de seguridad. Sin embargo, la declaración puede producirse en cualquier momento en el que esté disponible toda la información pertinente. El administrador del incidente de seguridad debe establecer pruebas más allá de la duda razonable de que se ha producido un evento del que informar para iniciar la ejecución del Proceso de notificación de incidentes del cliente.

Durante la investigación, el equipo de respuesta de seguridad trabaja junto a asistentes legales de todo el mundo para ayudar a garantizar que los análisis se realizan siguiendo los compromisos y las obligaciones legales con los clientes. También hay importantes restricciones sobre el visionado de datos de clientes y sistemas, además de sobre su manejo en varios entornos operativos. Los datos confidenciales y de los clientes no se transfieren fuera del entorno de producción sin la aprobación escrita del administrador de incidentes registrada en el tique de incidente correspondiente.

Microsoft comprueba que el riesgo para los clientes y negocios se ha contenido con éxito y que las medidas correctivas se han implementado. En caso necesario, se llevan a cabo pasos de atenuación de emergencia para resolver los riesgos de seguridad inmediatos asociados con el evento.

Microsoft también realiza un análisis final interno para las vulneraciones de datos. Como parte de este ejercicio, se evalúan los procedimientos operativos y la suficiencia de respuesta y se identifican e implementan las actualizaciones necesarias para la respuesta ante incidentes de seguridad o procesos relacionados. Los análisis finales internos para las vulneraciones de datos son registros muy confidenciales no disponibles para los clientes. Los análisis finales pueden, sin embargo, resumirse e incluirse en otras notificaciones de eventos del cliente. Estos informes se proporcionan a auditores externos para su revisión como parte del ciclo de auditoría rutinario de Azure.

## <a name="customer-notification"></a>Notificación al cliente

Microsoft Azure notifica a clientes y organismos reguladores acerca de las vulneraciones de datos según sea necesario. Microsoft depende de una gran compartimentación interna en la operación de Azure. También son sólidos los registros de flujo de datos. Una ventaja de este diseño es que la mayoría de incidentes pueden rastrearse hasta clientes específicos. El objetivo es proporcionar a los clientes afectados con un aviso preciso, puntual y efectivo cuando han sufrido una vulneración de datos.

Después de la declaración de un CRSI, el proceso de notificación se lleva a cabo lo antes posible mientras se consideran los riesgos de seguridad de actuar con rapidez. Por lo general, el proceso de elaboración de notificaciones se produce durante la investigación del incidente. Los avisos al cliente se entregan en menos de 72 horas a partir del momento en que se declara una vulneración *excepto* en las siguientes circunstancias:

- Microsoft cree que el acto de realizar una notificación aumentará el riesgo para otros clientes. Por ejemplo, la notificación puede alertar a un adversario y provocar una incapacidad para poner remedio.

- Otras circunstancias inusuales o extremas expuestas por el departamento legal de Microsoft, asuntos legales y externos corporativos (CELA), y el administrador de incidentes ejecutivo.

Microsoft Azure proporciona a los clientes información detallada, lo que les permite realizar investigaciones internas y ayudar a cumplir los compromisos de usuario final, mientras no retrase indebidamente el proceso de notificación.

La notificación de una vulneración de datos personales se entregará al cliente por cualquier medio elegido por Microsoft, incluyendo el correo electrónico. La notificación de una vulneración de datos se enviará a la lista de contactos de seguridad proporcionada en Azure Security Center, que puede configurarse siguiendo las [directrices de implementación](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Si no se proporciona información de contacto en el centro de seguridad de Azure, la notificación se enviará a uno o varios administradores de una suscripción de Azure. Para asegurarse de que pueda entregarse la notificación correctamente, es responsabilidad del cliente proporcionar información de contacto administrativa correcta en cada suscripción y portal de servicios en línea aplicables.

El equipo de Microsoft Azure o Azure Government también puede elegir notificar a personal de Microsoft adicional, como el servicio al cliente (CSS) y el administrador de cuentas del cliente (AM) o el administrador técnico de cuentas (TAM). Estos individuos a menudo tienen una relación cercana con el cliente y puedes facilitar una solución más rápida.<span id="_Appendix_A" class="anchor"></span>

## <a name="microsoft-intune-data-breach"></a>Infracción de datos de Microsoft Intune

Microsoft Intune es un componente clave de la oferta de servicios en la nube de Microsoft Enterprise Mobility y suite de seguridad. Para admitir la estrategia de gobierno de datos, todos los servicios de nube de Microsoft se desarrollan con las metodologías de seguridad y privacidad predeterminada y privacidad y seguridad por diseño de Microsoft.

Por tanto, la oferta del servicio de nube de Microsoft Intune sigue las mismas medidas técnicas y de organización que los equipos del servicio de Microsoft Azure llevan a cabo para asegurarse ante los procesos de vulneración de datos. Por tanto, cualquier información documentada en el documento de notificación "Vulneración de datos de Microsoft Azure" es análogo al servicio de Microsoft Intune. Por ejemplo, Microsoft Intune tiene el mismo ciclo de vida y proceso de respuesta ante incidentes de seguridad (desde la fase 1: detección hasta la fase 5<strong>:</strong> Cierre y análisis final) y el mismo proceso de notificación de incidentes de seguridad. Además, Microsoft Intune también cumple sus obligaciones en cuanto a notificaciones para los clientes de Microsoft O365 que usen Intune al trabajar directamente con el equipo de Microsoft O365.

Para obtener más información sobre cómo Microsoft detecta y responde ante una vulneración de datos personales, vea [Notificación de vulneraciones de datos según el RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) en el Portal de confianza del servicio.


## <a name="learn-more"></a>Más información

[Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
