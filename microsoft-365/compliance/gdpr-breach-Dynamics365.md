---
title: Dynamics 365 y notificación de vulneraciones según el RGPD
description: Se explica cómo Dynamics 365 protege contra una infracción de datos personales y cómo Microsoft responde y le notifica si se produce una infracción.
keywords: Dynamics 365, Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 5bdaa174a4701466ce9f7bd4975221ab95c1cb45
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871412"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>Dynamics 365 y notificación de vulneraciones según el RGPD

Dynamics 365 se toma muy en serio sus obligaciones según el Reglamento general de protección de datos (RGPD) sobre la vulneración de datos de Microsoft Dynamics 365

Microsoft trabaja continuamente para ofrecer servicios de categoría empresarial altamente seguros a los clientes de Dynamics 365. En esta sección, se ofrece un resumen de cómo Microsoft Dynamics 365 protege ante incidentes de seguridad o vulneraciones de datos, y el proceso que seguimos para responder y notificar a nuestros clientes.

#### <a name="microsoft-dynamics-365-built-in-security-features"></a>Características de seguridad integradas en Microsoft Dynamics 365

Microsoft Dynamics 365 usa la infraestructura de servicios en la nube y las características de seguridad integradas para garantizar la integridad de los datos con medidas de seguridad y mecanismos de protección. Además, Dynamics 365 ofrece acceso a datos y colaboración eficientes con integridad de los datos y privacidad en las áreas siguientes: [identidad segura, protección de datos, seguridad basada en roles y administración de amenazas](https://www.microsoft.com/trustcenter/security/dynamics365-security).

#### <a name="incident-response-training"></a>Aprendizaje de respuesta ante incidentes

Todos los empleados que trabajan en Microsoft Dynamics 365 reciben aprendizaje en relación con incidentes de seguridad y procedimientos de respuesta adecuados para su rol. Todos los empleados de Microsoft Dynamics 365 reciben aprendizaje al incorporarse y un aprendizaje de actualización cada año a partir de entonces. El aprendizaje se diseñó para ofrecer al empleado una comprensión básica del método de Microsoft en relación con la seguridad para que, una vez completado el aprendizaje, todos los empleados comprendan:

-   la definición de un incidente de seguridad;

-   la responsabilidad de todos los empleados de denunciar los incidentes de seguridad;

-   cómo escalar un posible incidente de seguridad al equipo de respuesta ante incidentes de seguridad de Dynamics 365;

-   cómo el equipo de respuesta ante incidentes de seguridad de Dynamics 365 responde ante los incidentes de seguridad;

-   preocupaciones especiales en relación con la privacidad, especialmente la privacidad de los clientes;

-   dónde encontrar información adicional sobre seguridad y privacidad, y contactos de escalación.

#### <a name="how-does-microsoft-dynamics-365-define-security-incident-potential-breaches"></a>Definición de Microsoft Dynamics 365 de un incidente de seguridad o posibles vulneraciones

Un incidente de seguridad o una vulneración de datos hace referencia a eventos, como un acceso ilegal a los datos del cliente almacenados en equipos de Microsoft o en instalaciones de Microsoft, o bien el acceso no autorizado a dichos equipos o instalaciones que puede producir la pérdida, divulgación o modificación de los datos de clientes. El objetivo de Microsoft al responder ante los incidentes de seguridad o infracciones de datos es proteger los datos de los clientes y los servicios de Dynamics 365. El enfoque de Microsoft en relación con la administración de un incidente de seguridad cumple con la publicación especial [800-61](https://www.nist.gov/) del [Instituto nacional de normalización y tecnología](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) (NIST).

Microsoft no supervisa ni responde ante incidentes de seguridad en el dominio de responsabilidad del cliente. Un peligro para la seguridad causado solo por un cliente no se trataría como un incidente de seguridad de Dynamics 365, y el espacio empresarial del cliente tendría que administrar el esfuerzo de respuesta. Una respuesta ante incidentes de clientes podría precisar la colaboración con el servicio de atención al cliente de Microsoft Dynamics 365, siempre que el cliente disponga de los contratos de servicio adecuados.

#### <a name="detection-of-potential-breaches"></a>Detección de posibles vulneraciones

Dynamics 365 responde ante una posible vulneración de datos según el proceso de respuesta ante incidentes de seguridad, un subconjunto del plan de administración de incidentes de Microsoft Dynamics 365. La respuesta ante incidentes de seguridad de Dynamics 365 se implementa con un proceso de cinco fases: detección, evaluación, diagnóstico, estabilización y cierre. El equipo de respuesta ante incidentes de seguridad puede cambiar entre las fases de diagnóstico y estabilización a medida que avance la investigación. Aquí encontrará información general sobre el proceso de respuesta ante incidentes de seguridad:

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">Fase</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">1</td>
<td align="left">Detección</td>
<td align="left">Primera indicación de la investigación de un evento.</td>
</tr>
<tr class="even">
<td align="left">2</td>
<td align="left">Evaluación</td>
<td align="left">Un miembro del equipo de respuesta ante incidentes evalúa el impacto y la gravedad del evento. Según las pruebas, la evaluación puede o no provocar una escalación al equipo de respuesta de seguridad.</td>
</tr>
<tr class="odd">
<td align="left">3</td>
<td align="left">Diagnóstico o investigación</td>
<td align="left"><p>Los expertos en respuestas de seguridad llevan a cabo la investigación técnica o forense, la identificación de estrategias de contención, la mitigación y la aplicación de soluciones alternativas.</p>
<p>Si el equipo de seguridad cree que los datos del cliente pueden haberse expuesto a una persona ilegal o no autorizada, se inicia en paralelo el proceso de notificación de incidentes de clientes.</p></td>
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

En las notas del producto denominadas [Administración de incidentes de seguridad de Dynamics](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers), se proporciona más información sobre la forma en que Microsoft investiga, administra y responde ante incidentes de seguridad en Dynamics 365.

Los procesos de detección usados por Microsoft Dynamics 365 se diseñaron para obtener información sobre eventos que ponen en riesgo la integridad, la confidencialidad y la disponibilidad de los servicios de Dynamics 365. Algunos eventos pueden desencadenar una investigación:

-   Alertas automáticas del sistema mediante supervisión interna y marcos de alertas. Estas alertas pueden interferir con alarmas basadas en firmas, como antimalware, detección de intrusiones o mediante algoritmos diseñados para identificar actividades previstas y generar alertas ante anomalías.

-   Informes propios que ejecutan los servicios de Microsoft Dynamics 365 implementados en la nube pública y servicios de Microsoft Dynamics 365 implementados en la nube soberana.

-   Las vulnerabilidades de seguridad se notifican al [Centro de respuestas de seguridad de Microsoft (MSRC)](https://technet.microsoft.com/security/dn440717) mediante <secure@microsoft.com>. El MSRC trabaja con socios e investigadores de seguridad de todo el mundo para evitar incidentes de seguridad y mejorar la seguridad de los productos de Microsoft.

-   Informes de clientes que describen actividades sospechosas atribuidas a los servicios de Microsoft Dynamics 365 (en oposición a la actividad que se produce dentro del ámbito de responsabilidad del cliente).

-   Actividad de los [equipos de seguridad rojo y azul](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Esta estrategia usa un equipo rojo de expertos altamente cualificado en seguridad ofensiva de Microsoft para descubrir y atacar debilidades potenciales en los servicios de Microsoft Dynamics 365. El equipo azul de respuesta de seguridad necesita detectar y defenderse contra la actividad del equipo rojo. Las acciones de los equipos rojo y azul se usan para comprobar que los esfuerzos de respuesta de seguridad de Microsoft Dynamics 365 son efectivos a la hora de administrar incidentes de seguridad. Las actividades de los equipos de seguridad rojo y azul se operan según los requisitos de responsabilidad para garantizar la protección de los datos de clientes.

-   Escalaciones por operadores de los servicios de Microsoft Dynamics 365. Los empleados de Microsoft reciben aprendizaje para identificar y escalar posibles problemas de seguridad.

#### <a name="microsoft-dynamics-365-data-breach-response"></a>Respuesta a una vulneración de datos de Microsoft Dynamics 365

Microsoft asigna la prioridad y los niveles de gravedad adecuados a la investigación al determinar el impacto funcional, la capacidad de recuperación y el impacto de la información del incidente. Tanto la prioridad como la gravedad pueden cambiar a lo largo de la investigación según las conclusiones y nuevos conocimientos. Los eventos de seguridad que implican un riesgo inminente o confirmado para los datos de clientes se consideran de gravedad alta y se trabaja en ellos de forma ininterrumpida para solucionarlos. Microsoft Dynamics 365 define una infracción de privacidad como una vulneración de “datos personales del usuario final de un servicio en línea o los empleados de Microsoft”.

El equipo de respuesta de seguridad trabaja con los ingenieros de seguridad de Microsoft Dynamics 365 y expertos en la materia para clasificar el evento basándose en datos concretos a partir de las evidencias. Un evento de seguridad se puede clasificar como:

-   **Falso positivo:** un evento que cumple los criterios de detección, pero que pertenece a un procedimiento empresarial normal y puede que sea necesario filtrarlo. El equipo de servicio identificará la causa principal de los falsos positivos y los solucionará de forma sistemática con el ajuste de los orígenes<span id="_Toc350859432" class="anchor"></span> de detección, según sea necesario.

-   **Incidente de seguridad:** un incidente en el que se produce un acceso ilegal a los datos de los clientes o de soporte técnico almacenados en equipos o instalaciones de Microsoft; o un acceso no autorizado a dichos equipos o instalaciones que da como resultado la pérdida, divulgación o modificación de datos de clientes o de soporte técnico.

-   **Incidente de seguridad denunciado por el cliente:** un acceso o un uso ilegal o no autorizado de sistemas, equipos o instalaciones de Microsoft que da como resultado la divulgación, modificación o pérdida de datos de clientes.

-   **Incidente de privacidad:** un subtipo de incidente de seguridad relacionado con datos personales. Los procedimientos de control no son distintos de un incidente de seguridad.

Para que se declare un incidente de seguridad denunciado por el cliente, Microsoft necesita determinar si se produjo (o es muy probable que se produjera) el acceso no autorizado a datos de clientes, o bien si existe una obligación legal o contractual para la notificación. Es preferible, aunque no necesario, conocer el impacto, el acceso a los recursos y los pasos de reparación del cliente específico. Por lo general, se declara un incidente de seguridad denunciado por el cliente una vez finalizada la fase de diagnóstico de un incidente de seguridad; pero, si la información relevante se encuentra disponible, la declaración puede producirse en cualquier momento. Para poder iniciar la ejecución del proceso de notificación de incidentes de clientes, el administrador de incidentes de seguridad necesita establecer pruebas más allá de la duda razonable de que se produjo un evento denunciable.

Durante la investigación, el equipo de respuesta de seguridad trabaja con asesores jurídicos de todo el mundo para garantizar que los análisis forenses se realicen según los compromisos y obligaciones legales con los clientes. También hay restricciones importantes sobre la visualización y el tratamiento de los datos de clientes y los sistemas en varios entornos operativos. Los datos confidenciales y de los clientes no se transfieren fuera del entorno de producción sin la aprobación explícita y por escrito del administrador de incidentes, registrada en el vale del incidente correspondiente.

Microsoft comprueba que se contenga correctamente el riesgo para los clientes y las empresas, y que se implementen las medidas correctivas. Si es necesario, se llevan a cabo pasos de mitigación de emergencia para solucionar los riesgos de seguridad inmediatos asociados al evento.

Microsoft también realiza un análisis posterior interno de las infracciones de datos. Como parte de este ejercicio, se evalúan los procedimientos operativos y la suficiencia de respuesta, y se identifican e implementan las actualizaciones necesarias en las directivas de seguridad internas de Microsoft o los procesos relacionados. Los análisis posteriores internos de las infracciones de datos son registros altamente confidenciales que no están disponibles para los clientes. Pero los análisis posteriores pueden resumirse e incluirse en otras notificaciones de eventos del cliente. Estos informes se proporcionan a auditores externos para su revisión como parte del ciclo de auditoría rutinario de Dynamics 365.

#### <a name="customer-notification"></a>Notificación al cliente

Microsoft Dynamics 365 notifica a clientes y autoridades reguladoras sobre las infracciones de datos según sea necesario. Microsoft depende de una gran compartimentación interna al operar los servicios de Dynamics 365. También son sólidos los registros de flujo de datos. Una ventaja de este diseño es que la mayoría de los incidentes pueden identificarse dentro del ámbito de clientes específicos. El objetivo es proporcionar a los clientes afectados un aviso preciso, procesable y puntual cuando se produzcan infracciones de datos.

Después de declarar un incidente de seguridad denunciado por el cliente, el proceso de notificación se lleva a cabo lo antes posible, mientras se tienen en cuenta los riesgos de seguridad de actuar con rapidez. Por lo general, el proceso de elaboración de notificaciones se produce durante la investigación del incidente. Los avisos para clientes se entregan rápidamente a partir del momento en que se declara una infracción, *excepto* en las siguientes circunstancias:

-   Microsoft considera que el acto de realizar una notificación incrementará el riesgo para otros clientes. Por ejemplo, el acto de enviar una notificación puede alertar a un adversario e impedir una corrección adecuada.

-   Otras circunstancias poco frecuentes o extremas determinadas por el departamento jurídico de Microsoft y por el director ejecutivo de incidentes.

Microsoft Dynamics 365 proporciona a los clientes información detallada, lo que les permite realizar investigaciones internas y ayudar a cumplir los compromisos de usuario final, sin retrasar de forma indebida el proceso de notificación.

La notificación de una infracción de datos personales se entregará al cliente por cualquiera de los medios que seleccione Microsoft, incluido por correo electrónico. La notificación de una infracción de datos se entregará a la lista de administradores o contactos del cliente (solo de los espacios empresariales afectados) especificados en el Centro de seguridad de Office, lo que puede configurar el cliente o el administrador del espacio empresarial. Para garantizar que la notificación se pueda entregar correctamente, es responsabilidad del cliente comprobar que sea correcta la información del contacto administrativo de la suscripción y el portal de servicios en línea correspondientes.

El equipo de Microsoft Dynamics 365 también puede enviar notificaciones adicionales a personal de Microsoft, como al servicio de atención al cliente y al administrador de cuentas del cliente o responsable técnico de cuenta (TAM). Con frecuencia, estas personas tienen una relación estrecha con el cliente y pueden facilitar una corrección más rápida.<span id="_Appendix_A" class="anchor"></span>

#### <a name="learn-more"></a>Más información
[Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)