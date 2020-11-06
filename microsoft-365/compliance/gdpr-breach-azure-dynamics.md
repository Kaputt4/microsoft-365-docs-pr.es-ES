---
title: Notificación de infracciones de datos según el RGPD de Azure y Dynamics 365
description: Le explicamos cómo Azure y Dynamics 365 protege contra una vulneración de datos personales y cómo Microsoft responde y le notifica si se produce una vulneración.
keywords: Azure, Microsoft 365, Dynamics 365, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920273"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Notificación de infracciones de datos según el RGPD de Azure y Dynamics 365

Microsoft Azure toma muy en serio sus obligaciones sobre la normativa general de protección de datos (RGPD). Microsoft Azure toma medidas de seguridad para protegerse de las infracciones de datos, incluyendo controles de seguridad físicos y lógicos, así como automatización los procesos de seguridad, directivas de seguridad y privacidad de la información completas y formación en seguridad y privacidad para todo el personal.

La seguridad se integra en Microsoft Azure desde cero, comenzando con el [Ciclo de vida de desarrollo de seguridad](https://www.microsoft.com/sdl/), un proceso de desarrollo obligatorio que incorpora metodologías de privacidad por diseño y privacidad de forma predeterminada. El criterio rector de la estrategia de seguridad de Microsoft es "asumir la infracción" que es una extensión de la estrategia de defensa exhaustiva. Al poner a prueba capacidades de seguridad de Azure constantemente, Microsoft puede mantenerse por delante de las amenazas emergentes. Para obtener más información sobre la seguridad de Azure, revise estos [recursos](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft tiene un servicio de respuesta a incidentes 24/7 global adecuado para reducir los efectos de los ataques contra Microsoft Azure. Acreditado mediante varias auditorías de seguridad y cumplimiento (por ejemplo, [ISO/CEI 27018](offering-iso-27018.md)), Microsoft emplea operaciones y procesos de gran rigor en sus centros de datos para evitar el acceso no autorizado, incluyendo la supervisión en vídeo 24/7, personal de seguridad formado, tarjetas inteligentes y controles biométricos.

## <a name="detection-of-potential-breaches"></a>Detección de posibles vulneraciones

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure también ofrece varios servicios (por ejemplo, [Azure Defender](https://azure.microsoft.com/services/security-center/)) que los clientes pueden usar para desarrollar y administrar la respuesta a incidentes de seguridad.

Azure responde a una posible vulneración de datos según el proceso de respuesta a incidentes de seguridad, un subconjunto del plan de administración de incidentes de Microsoft Azure. La respuesta a incidentes de seguridad de Azure se implementa con un proceso de cinco fases: detección, evaluación, diagnóstico, estabilización y cierre. El equipo de respuesta a incidentes de seguridad puede alternar entre las fases de diagnóstico y estabilización a medida que avanza a la investigación. A continuación se expone información general sobre el proceso de respuesta de seguridad:

|**Stage**|**Descripción**|
| ------- | ------------- |
| **_1: Detección_* _ | Primera indicación de un posible incidente. |
| _*_2: evaluación_*_ | Un miembro del equipo de respuesta ante incidentes evalúa el impacto y la gravedad del evento. Según las pruebas, la evaluación puede o no provocar una escalación al equipo de respuesta de seguridad. |
| _*_3: diagnóstico_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4: estabilización y recuperación_*_ | El equipo de respuesta ante incidentes crea un plan de recuperación para mitigar el problema. De forma inmediata y en paralelo al diagnóstico, pueden darse pasos de contención de crisis, como poner en cuarentena los sistemas afectados. Pueden planearse mitigaciones a largo plazo después de solucionar el riesgo inmediato. |
| _*_5: cierre y análisis posterior_*_ | El equipo de respuesta ante incidentes crea un análisis posterior que expone los detalles del incidente, con la intención de revisar directivas, procedimientos y procesos para evitar que el evento vuelva a producirse. |

Las notas del producto [Respuesta de seguridad de Microsoft Azure en la nube](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) dan más detalles acerca de cómo Microsoft investiga, administra y responde a los incidentes de seguridad en Azure.

Los procesos de detección usados por Microsoft Azure están diseñados para detectar sobre eventos que ponen en riesgo la integridad, confidencialidad y disponibilidad de los servicios de Azure. Algunas situaciones pueden desencadenar una investigación:

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- Informes internos de los servicios Microsoft ejecutándose en Microsoft Azure y Azure Government.
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- Los informes de cliente a través del [Portal de soporte técnico al cliente](https://www.windowsazure.com/support/contact/) o el portal de administración de Microsoft Azure y Azure Government, que describen la actividad sospechosa atribuida a la infraestructura de Azure (en lugar de la actividad que se produce en el ámbito de responsabilidad del cliente).
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Escalado por parte de operadores de servicios de Azure. Los empleados de Microsoft están preparados para identificar y escalar los posibles problemas de seguridad.

## <a name="azures-data-breach-response"></a>Respuesta de infracción de datos de Azure

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure clasifica el impacto de la información del incidente en las siguientes categorías de infracción:

| _ *Categoría**             | **Definición**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Ninguna_* _               | No se ha extraído, cambiado, eliminado o comprometido ninguna información.                                                      |
| _*_Infracción de privacidad_*_     | Se han comprometido o se han extraído datos personales sensibles de contribuyentes, empleados, beneficiarios, etc                                |
| _*_Infracción de propietario_*_ | Se ha comprometido o accedido a información del propietario sin clasificar, como información de infraestructura crítica protegida (PCII).  |
| _*_Pérdida de integridad_*_     | Se ha modificado o eliminado información confidencial o de propiedad.                                                                     |

El equipo de respuesta de seguridad trabaja con los ingenieros de seguridad de Microsoft Azure y PYME para clasificar el evento con datos reales de las pruebas. Un evento de seguridad se puede clasificar como:

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **Incidente de seguridad** : un incidente en el que se produce un acceso ilegal a los datos de los clientes o de soporte técnico almacenados en equipos o instalaciones de Microsoft; o un acceso no autorizado a dichos equipos o instalaciones, que da como resultado la pérdida, divulgación o modificación de datos de clientes o de soporte técnico.
- **Incidente de seguridad o privacidad denunciado por el cliente** : un acceso o un uso ilegal o no autorizado de sistemas, equipos o instalaciones de Microsoft que da como resultado la divulgación, modificación o pérdida de datos de clientes.
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

Durante la investigación, el equipo de respuesta de seguridad trabaja junto a asistentes legales de todo el mundo para ayudar a garantizar que los análisis se realizan siguiendo los compromisos y las obligaciones legales con los clientes. También hay importantes restricciones sobre el visionado de datos de clientes y sistemas, además de sobre su manejo en varios entornos operativos. Los datos confidenciales y de los clientes no se transfieren fuera del entorno de producción sin la aprobación escrita del administrador de incidencias registrada en el tique de incidencia correspondiente.

Microsoft comprueba que el riesgo para los clientes y negocios se ha contenido con éxito y que las medidas correctivas se han implementado. En caso necesario, se llevan a cabo pasos de atenuación de emergencia para resolver los riesgos de seguridad inmediatos asociados con el evento.

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>Notificación al cliente

Microsoft Azure notifica a clientes y organismos reguladores acerca de las vulneraciones de datos según sea necesario. Microsoft depende de una gran compartimentación interna en la operación de Azure. También son sólidos los registros de flujo de datos. Una ventaja de este diseño es que la mayoría de incidentes pueden rastrearse hasta clientes específicos. El objetivo es proporcionar a los clientes afectados con un aviso preciso, puntual y efectivo cuando han sufrido una vulneración de datos.

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- Otras circunstancias inusuales o extremas expuestas por el departamento legal de Microsoft, asuntos legales y externos corporativos (CELA), y el administrador de incidentes ejecutivo.
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure proporciona a los clientes información detallada, lo que les permite realizar investigaciones internas y ayudar a cumplir los compromisos de usuario final, mientras no retrase indebidamente el proceso de notificación.

La notificación de una infracción de datos personales se entregará al cliente por cualquier medio elegido por Microsoft, incluyendo el correo electrónico. La notificación de una infracción de datos se enviará a la lista de contactos de seguridad proporcionada en Azure Defender, que puede configurarse siguiendo las [directrices de implementación](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Si no se proporciona información de contacto en Azure Defender, la notificación se enviará a uno o varios administradores de una suscripción de Azure. Para asegurarse de que pueda entregarse la notificación correctamente, es responsabilidad del cliente proporcionar información de contacto administrativa correcta en cada suscripción y portal de servicios en línea aplicables.

El grupo de Microsoft Azure o Azure Government también puede notificar al personal adicional de Microsoft, como el servicio de atención al cliente (CSS), el administrador de cuentas del cliente (o) o el administrador de cuentas técnicas (TAM). Por lo general, estas personas suelen tener relaciones estrechas con los clientes y pueden hacer que las correcciones se lleven a cabo más rápidamente.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Características de seguridad integradas en Microsoft Dynamics 365

Microsoft Dynamics 365 usa la infraestructura de servicios en la nube y las características de seguridad integradas para garantizar la integridad de los datos con medidas de seguridad y mecanismos de protección. Además, Dynamics 365 ofrece acceso a datos y colaboración eficientes con integridad de los datos y privacidad en las áreas siguientes: [identidad segura, protección de datos, seguridad basada en roles y administración de amenazas](https://www.microsoft.com/trustcenter/security/dynamics365-security).

La oferta de Microsoft Dynamics 365 sigue las mismas medidas técnicas y de organización que los equipos del servicio de Microsoft Azure llevan a cabo para proteger contra posibles vulneración de datos. Por tanto, cualquier información registrada en el documento de notificación "Vulneración de datos de Microsoft Azure" es en este caso también aplicable al servicio de Microsoft Dynamics 365.

## <a name="learn-more"></a>Más información

[Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
