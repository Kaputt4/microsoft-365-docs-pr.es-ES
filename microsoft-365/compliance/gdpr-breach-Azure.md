---
title: Azure y notificación de infracciones de datos según el RGPD
description: Se explica cómo Azure protege contra una infracción de datos personales y cómo responde Microsoft y le notifica si se produce una infracción.
keywords: Azure, Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 5e8c04bcd20f56580e939bc4a2685eb232d5e589
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431501"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a>Azure y notificación de infracciones de datos según el RGPD

Microsoft Azure toma muy en serio sus obligaciones sobre la normativa general de protección de datos (RGPD). Microsoft Azure toma medidas de seguridad para protegerse de las infracciones de datos, incluyendo controles de seguridad físicos y lógicos, así como automatización los procesos de seguridad, directivas de seguridad y privacidad de la información completas y formación en seguridad y privacidad para todo el personal.

La seguridad se integra en Microsoft Azure desde cero, comenzando con el [Ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/), un proceso de desarrollo obligatorio que incorpora metodologías de privacidad por diseño y privacidad de forma predeterminada. El criterio rector de la estrategia de seguridad de Microsoft es "asumir la infracción" que es una extensión de la estrategia de defensa exhaustiva. Al poner a prueba capacidades de seguridad de Azure constantemente, Microsoft puede mantenerse por delante de las amenazas emergentes. Para obtener más información sobre la seguridad de Azure, revise estos [recursos](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft tiene un servicio de respuesta a incidencias 24/7 global adecuado para reducir los efectos de los ataques contra Microsoft Azure. Acreditado mediante varias auditorías de seguridad y cumplimiento (por ejemplo, [ISO/CEI 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)), Microsoft emplea operaciones y procesos de gran rigor en sus centros de datos para evitar el acceso no autorizado, incluyendo la supervisión en vídeo 24/7, personal de seguridad formado, tarjetas inteligentes y controles biométricos.

#### <a name="detection-of-potential-breaches"></a>Detección de posibles infracciones
-------------------------------

Debido a la naturaleza de la nube moderna, no todas las infracciones de datos que se dan en el entorno de la nube del cliente tienen que ver con los servicios de Microsoft Azure. Microsoft utiliza un modelo de responsabilidad compartida para los servicios de Azure para definir las responsabilidades operativas y de seguridad. La responsabilidad compartida es especialmente importante al tratar la seguridad de un servicio de nube porque tanto el proveedor de servicios y el cliente son responsables de partes de la seguridad en la nube.

Microsoft no supervisa o responde a las incidencias de seguridad responsabilidad del cliente. Una infracción del cliente no puede procesarse como incidencia de seguridad de Azure y es responsabilidad del inquilino del cliente administrar la respuesta. La respuesta a la incidencia del cliente puede implicar la colaboración con [atención al cliente](https://azure.microsoft.com/support/options/) de Microsoft Azure, según los contratos de servicio correspondientes. Microsoft Azure también ofrece varios servicios (por ejemplo, [Azure Security Center](https://azure.microsoft.com/services/security-center/)) que los clientes pueden utilizar para desarrollar y administrar la respuesta a incidencias de seguridad.

Azure responde a una posible infracción de datos según el proceso de respuesta a incidencias de seguridad, un subconjunto del plan de administración de incidencias Microsoft Azure. La respuesta a incidencias de seguridad de Azure se implementa con un proceso de cinco fases: detección, evaluación, diagnóstico, estabilización y cierre. El equipo de respuesta a incidencias de seguridad puede alternar entre las fases de diagnóstico y estabilización a medida que avanza a la investigación. A continuación se expone información general sobre el proceso de respuesta de seguridad:

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Etapa</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Detección</td>
<td align="left">Primera indicación de una posible incidencia.</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Evaluación</td>
<td align="left">Un miembro del equipo de respuesta ante incidentes evalúa el impacto y la gravedad del evento. Según las pruebas, la evaluación puede o no provocar una escalación al equipo de respuesta de seguridad.</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Diagnóstico</td>
<td align="left"><p>Expertos en respuestas de seguridad llevan a cabo la investigación técnica o forense, identifican estrategias de contención, mitigación y alternativas.</p>
<p>Si el equipo de seguridad cree que los datos del cliente pueden haberse expuesto a una ejecución individual ilegal o no autorizada, se inicia el proceso de notificación de incidencias del cliente de forma paralela.</p></td>
</tr>
<tr class="even">
<td align="left">4</td>
<td align="left">Estabilización y recuperación</td>
<td align="left">El equipo de respuesta ante incidentes crea un plan de recuperación para mitigar el problema. De forma inmediata y en paralelo al diagnóstico, pueden darse pasos de contención de crisis, como poner en cuarentena los sistemas afectados. Pueden planearse mitigaciones a largo plazo después de solucionar el riesgo inmediato.</td>
</tr>
<tr class="odd">
<td align="left">5</td>
<td align="left">Cierre y análisis posterior</td>
<td align="left">El equipo de respuesta ante incidentes crea un análisis posterior que expone los detalles del incidente, con la intención de revisar directivas, procedimientos y procesos para evitar que el evento vuelva a producirse.</td>
</tr>
</tbody>
</table>

Las notas del producto [Respuesta de seguridad de Microsoft Azure en la nube](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) dan más detalles acerca de cómo Microsoft investiga, administra y responde a las incidencias de seguridad en Azure.

Los procesos de detección usados por Microsoft Azure están diseñados para obtener información sobre eventos que ponen en riesgo la integridad, confidencialidad y disponibilidad de los servicios de Azure. Algunas situaciones pueden desencadenar una investigación:

-   Alertas de sistema automatizadas a través de supervisión interna y marcos de alertas. Estas alertas pueden interferir con alarmas basadas en firmas como antimalware, detección de intrusiones o mediante algoritmos diseñados para identificar actividad esperada y alertar de anomalías.

-   Informes internos de los servicios Microsoft ejecutándose en Microsoft Azure y Azure Government.

-   Las vulnerabilidades de seguridad se notifican al [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) a través de <secure@microsoft.com>. El MSRC trabaja con socios e investigadores de seguridad de todo el mundo para ayudar a evitar incidencias de seguridad y para mejorar la seguridad de los productos de Microsoft.

-   Los informes de cliente a través del [Portal de soporte técnico al cliente](http://www.windowsazure.com/support/contact/) o el portal de administración de Microsoft Azure y Azure Government, que describen la actividad sospechosa atribuida a la infraestructura de Azure (en lugar de la actividad que se producen en el ámbito de responsabilidad del cliente).

-   Actividad [equipo rojo y equipo de azul](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) de seguridad. Esta estrategia usa un equipo rojo de expertos en seguridad ofensiva de Microsoft para descubrir y atacar debilidades potenciales en Azure. El equipo azul de respuesta de seguridad debe detectar y defenderse contra la actividad del equipo rojo. Las acciones de ambos equipos se utilizan para verificar que los esfuerzos de respuesta de seguridad de Azure son efectivos a la hora de administrar incidencias de seguridad. Las actividades de los equipos rojo y azul de seguridad operan según las reglas de contratación para ayudar a asegurar la protección de datos de clientes.

-   Escalado por parte de operadores de servicios de Azure. Los empleados de Microsoft están preparados para identificar y escalar los posibles problemas de seguridad.

#### <a name="azures-data-breach-response"></a>Respuesta de infracción de datos de Azure
----------------------------

Microsoft asigna la prioridad y los niveles de gravedad adecuados a la investigación al determinar el impacto funcional, la recuperación y el impacto de la información de la incidencia. Tanto la prioridad como la gravedad pueden cambiar a lo largo de la investigación en función de las conclusiones y de nuevos conocimientos. Los eventos de seguridad que implican riesgo inminente o confirmado a los datos se tratan como graves y se trabaja en ellos de forma ininterrumpida para resolverlos. Microsoft Azure clasifica el impacto de la información de la incidencia en las siguientes categorías de infracción:

<table>
<thead>
<tr class="header">
<th align="left">Categoría</th>
<th align="left">Definición</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Ninguno</td>
<td align="left">No se ha extraído, cambiado, eliminado o comprometido ninguna información.</td>
</tr>
<tr class="even">
<td align="left">Infracción de privacidad</td>
<td align="left">Se ha comprometido o accedido a datos personales confidenciales de contribuyentes, empleados, beneficiarios, etc.</td>
</tr>
<tr class="odd">
<td align="left">Infracción de propietario</td>
<td align="left">Se ha comprometido o accedido a información propietaria sin clasificar, como información de infraestructura crítica protegida (PCII).</td>
</tr>
<tr class="even">
<td align="left">Pérdida de integridad</td>
<td align="left">Se ha modificado o eliminado información confidencial o de propiedad.</td>
</tr>
</tbody>
</table>

El equipo de respuesta de seguridad trabaja con los ingenieros de seguridad de Microsoft Azure y PYME para clasificar el evento con datos reales de las pruebas. Un evento de seguridad se puede clasificar como:

-   **Falso positivo:** un evento que cumple los criterios de detección, pero es parte de un procedimiento normal del negocio y es preciso filtrarlo. El equipo de servicio identificar la causa de los falsos positivos y los soluciona de forma sistemática con ajustando los orígenes<span id="_Toc350859432" class="anchor"></span> de detección según sea necesario.

-   **Incidencia de seguridad:** una incidencia en la que se ha producido un acceso ilegal a los datos de los clientes o de soporte técnico almacenados en equipo o instalaciones de Microsoft; o un acceso no autorizado a dicho equipo o instalaciones que ha resultado en la pérdida, divulgación o alteración de datos de clientes o soporte técnico.

-   **Incidencia de seguridad de los clientes (CRSI):** un acceso o uso ilegal o no autorizado a sistemas, equipo o instalaciones de Microsoft que resulta en la divulgación, modificación o pérdida de datos de clientes.

-   **Infracción de privacidad:** un subtipo de incidencia de seguridad relacionado con datos personales. Los procedimientos de control no son diferentes de una incidencia de seguridad.

Para que se declare una CRSI, Microsoft debe determinar que el acceso no autorizado a los datos del cliente se ha producido, o es probable que lo haya hecho, o existe un compromiso legal o contractual que fuerce la notificación. Es preferible, aunque no se requiere, que se conozcan los pasos de impacto del cliente específico, acceso a los recursos y reparación. Por lo general, se declara que una incidencia es un CRSI tras la conclusión de la etapa de diagnóstico de una incidencia de seguridad; sin embargó, la declaración puede producirse en cualquier momento si la información pertinente se encuentra disponible. El administrador de la incidencia de seguridad debe establecer pruebas más allá de la duda razonable de que se ha producido un evento del que informar para iniciar la ejecución del proceso de notificación de incidencias del cliente.

Durante la investigación, el equipo de respuesta de seguridad trabaja junto a asistentes legales de todo el mundo para ayudar a garantizar que los análisis se realizan siguiendo los compromisos y las obligaciones legales con los clientes. También hay importantes restricciones sobre el visionado de datos de clientes y sistemas, además de sobre su manejo en varios entornos operativos. Los datos confidenciales y de los clientes no se transfieren fuera del entorno de producción sin la aprobación escrita del administrador de incidencias registrada en el tique de incidencia correspondiente.

Microsoft comprueba que el riesgo para los clientes y negocios se ha contenido con éxito y que las medidas correctivas se han implementado. En caso necesario, se llevan a cabo pasos de atenuación de emergencia para resolver los riesgos de seguridad inmediatos asociados con el evento.

Microsoft también realiza un análisis posterior interno de las infracciones de datos. Como parte de este ejercicio, se evalúan los procedimientos operativos y la suficiencia de respuesta y se identifican e implementan las actualizaciones necesarias para la respuesta ante incidencias de seguridad o procesos relacionados. Los análisis posteriores internos de las infracciones de datos son registros altamente confidenciales que no están disponibles para los clientes. Pero los análisis posteriores pueden resumirse e incluirse en otras notificaciones de eventos del cliente. Estos informes se proporcionan a auditores externos para su revisión como parte del ciclo de auditoría rutinario de Azure.

#### <a name="customer-notification"></a>Notificación al cliente
---------------------

Microsoft Azure notifica a clientes y organismos reguladores acerca de las infracciones de datos según sea necesario. Microsoft depende de una gran compartimentación interna en la operación de Azure. También son sólidos los registros de flujo de datos. Una ventaja de este diseño es que la mayoría de incidencias pueden rastrearse hasta clientes específicos. El objetivo es proporcionar a los clientes afectados con un aviso preciso, puntual y efectivo cuando han sufrido una infracción de datos.

Después de la declaración de un CRSI, el proceso de notificación se lleva a cabo lo antes posible mientras se consideran los riesgos de seguridad de actuar con rapidez. Por lo general, el proceso de elaboración de notificaciones se produce durante la investigación de la incidencia. Los avisos al cliente se entregan en menos de 72 horas a partir del momento en que se declara una infracción *excepto* en las siguientes circunstancias:

-   Microsoft cree que el acto de realizar una notificación aumentará el riesgo para otros clientes. Por ejemplo, la notificación puede alertar a un adversario y provocar una incapacidad para poner remedio.

-   Otras circunstancias inusuales o extremas expuestas por el departamento legal de Microsoft, asuntos legales y externos corporativos (CELA), y el administrador de incidencias ejecutivo.

Microsoft Azure proporciona a los clientes información detallada, lo que les permite realizar investigaciones internas y ayudar a cumplir los compromisos de usuario final, mientras no retrase indebidamente el proceso de notificación.

Se enviará una notificación de la violación de datos personales al cliente por cualquier medio que seleccione Microsoft, incluido por correo electrónico. La notificación de una infracción de datos se enviará a la lista de contactos de seguridad proporcionada en Azure Security Center, que puede configurarse siguiendo las [directrices de implementación](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details).  Si no se proporciona información de contacto en Azure Security Center, la notificación se enviará a uno o más administradores de una suscripción de Azure. Para garantizar que la notificación se pueda entregar correctamente, es responsabilidad del cliente comprobar que sea correcta la información del contacto administrativo de la suscripción y el portal de servicios en línea correspondientes.

El equipo de Microsoft Azure o Azure Government también puede elegir notificar a personal de Microsoft adicional, como el servicio al cliente (CSS) y el administrador de cuentas del cliente (AM) o el administrador técnico de cuentas (TAM). Estos individuos a menudo tienen una relación cercana con el cliente y puedes facilitar una solución más rápida.<span id="_Appendix_A" class="anchor"></span>

#### <a name="microsoft-intune-data-breach"></a>Infracción de datos de Microsoft Intune
----------------------------

Microsoft Intune es un componente clave de la oferta de servicios en la nube de Microsoft Enterprise Mobility y suite de seguridad. Para admitir la estrategia de gobierno de datos, todos los servicios de nube de Microsoft se desarrollan con las metodologías de seguridad y privacidad predeterminada y privacidad y seguridad por diseño de Microsoft.

Por tanto, la oferta del servicio de nube de Microsoft Intune sigue las mismas medidas técnicas y de organización que los equipos del servicio de Microsoft Azure llevan a cabo para asegurarse ante los procesos de vulneración de datos. Por tanto, cualquier información documentada en el documento de notificación "Vulneración de datos de Microsoft Azure" es análogo al servicio de Microsoft Intune. Por ejemplo, Microsoft Intune tiene el mismo ciclo de vida y proceso de respuesta ante incidencias de seguridad (desde la fase 1: detección hasta la fase 5<strong>:</strong> Cierre y análisis final) y el mismo proceso de notificación de incidencias de seguridad. Además, Microsoft Intune también cumple sus obligaciones en cuanto a notificaciones para los clientes de Microsoft O365 que usen Intune al trabajar directamente con el equipo de Microsoft O365.

Para obtener más información sobre cómo Microsoft detecta y responde ante una infracción de datos personales, vea [Notificación de infracciones de datos según el RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) en el Portal de confianza del servicio.


#### <a name="learn-more"></a>Más información
[Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
