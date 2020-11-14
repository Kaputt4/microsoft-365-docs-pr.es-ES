---
title: Notificación del servicio de tratamiento de datos para Windows Enterprise en virtud del RGPD
description: Cómo el servicio de tratamiento de datos para Windows Enterprise protege contra las infracciones de datos personales y cómo Microsoft responde y le avisa si se produce una infracción.
keywords: Servicio de tratamiento de datos para Windows Enterprise, Microsoft 365, documentación de Microsoft 365, RGPD
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 5d0a5563de2443e5af0f3b7efda0947d4f669cee
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070904"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Notificación de infracción del servicio de tratamiento de datos para Windows Enterprise en virtud del RGPD

>[!NOTE]
>This topic is intended for participants in the data processor service for Windows Enterprise preview program and requires acceptance of specific terms of use. To learn more about the program and agree to the terms of use, see [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Microsoft data processor service for Windows Enterprise takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft data processor service for Windows Enterprise takes extensive security measures to protect against data breaches. These include dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection detect and prevent malicious access, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel. 

Security is built into the Microsoft data processor service for Windows Enterprise from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft's security strategy is to 'assume breach', which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of the data processor service for Windows Enterprise, Microsoft can stay ahead of emerging threats. For more information on the data processor service for Windows Enterprise security, please review these [resources](https://www.microsoft.com/TrustCenter/Security/windows10-security) the data processor service for Windows Enterprise responds to a potential data breach according to the security incident response process. The data processor service for Windows Enterprise security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below: 

|**Stage**|**Descripción**|
| ------- | ------------- |
| **_1: Detección_* _ | Primera indicación de un posible incidente. |
| _*_2: evaluación_*_ | Un miembro del equipo de respuesta ante incidentes evalúa el impacto y la gravedad del evento. Según las pruebas, la evaluación puede o no provocar una escalación al equipo de respuesta de seguridad. |
| _*_3: diagnóstico_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4: estabilización y recuperación_*_ | El equipo de respuesta ante incidentes crea un plan de recuperación para mitigar el problema. De forma inmediata y en paralelo al diagnóstico, pueden darse pasos de contención de crisis, como poner en cuarentena los sistemas afectados. Pueden planearse mitigaciones a largo plazo después de solucionar el riesgo inmediato. |
| _*_5: Cierre y análisis posterior_*_ | El equipo de respuesta ante incidentes crea un análisis posterior que expone los detalles del incidente con la intención de revisar directivas, procedimientos y procesos y evitar que se vuelva a producir. |

The detection processes used by Microsoft data processor service for Windows Enterprise are designed to discover events that risk the confidentiality, integrity, and availability of the data processor service for Windows Enterprise. Several events can trigger an investigation: 

 - Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
 - Informes internos de los servicios Microsoft ejecutándose en Microsoft Azure y Azure Government.
 - Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
 - Los informes de cliente a través del Portal de soporte técnico al cliente o el portal de administración de Microsoft Azure y Azure Government, que describen la actividad sospechosa atribuida a la infraestructura de Azure (en lugar de la actividad que se produce en el ámbito de responsabilidad del cliente).
 - Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
 - Escalado por parte de operadores de servicios de Azure. Los empleados de Microsoft están preparados para identificar y escalar los posibles problemas de seguridad.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Respuesta a infracciones del servicio de tratamiento de datos para Windows Enterprise 

 Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft data processor service for Windows Enterprise categorizes the information impact of the incident into the following breach categories: 

| _ *Categoría**             | **Definición**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Ninguna_* _               | No se ha extraído, cambiado, eliminado o comprometido ninguna información. |
| _*_Vulneración de privacidad_*_     | Se ha eliminado o se ha accedido a datos personales confidenciales de contribuyentes, empleados, beneficiarios, etc. |
| _*_Vulneración de propiedad_*_ | Se ha eliminado o se ha accedido a información no clasificada de propiedad, como información de infraestructura crítica protegida (PCII). |
| _*_Pérdida de integridad_*_     | Se ha modificado o eliminado información confidencial o de propiedad. |

The Security Response Team works with Microsoft data processor service for Windows Enterprise Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as: 

 - _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-tuning them as needed. 
 - **Incidente de seguridad** : un incidente en el que se produce un acceso ilegal a los datos de los clientes o de soporte técnico almacenados en equipos o instalaciones de Microsoft; o un acceso no autorizado a dichos equipos o instalaciones, que da como resultado la pérdida, divulgación o modificación de datos de clientes o de soporte técnico. 
 - **Incidente de seguridad que debe notificarse al cliente (CRSI):** un acceso o uso ilegal o no autorizado a sistemas, equipos o instalaciones de Microsoft, que resulta en la divulgación, modificación o pérdida de datos de clientes. 
 - **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident. 

 Para que se declare una CRSI, Microsoft debe determinar que el acceso no autorizado a los datos del cliente se ha producido, o es probable que lo haya hecho, o existe un compromiso legal o contractual que fuerce la notificación. Es preferible, aunque no se requiere, que se conozcan los pasos de impacto del cliente específico, acceso a los recursos y reparación. Por lo general, se declara que una incidencia es un CRSI tras la conclusión de la etapa de diagnóstico de una incidencia de seguridad; sin embargó, la declaración puede producirse en cualquier momento si la información pertinente se encuentra disponible. El administrador de la incidencia de seguridad debe establecer pruebas más allá de la duda razonable de que se ha producido un evento del que informar para iniciar la ejecución del proceso de notificación de incidencias del cliente. 

Durante la investigación, el equipo de respuesta de seguridad trabaja junto a asistentes legales de todo el mundo para ayudar a garantizar que los análisis se realizan siguiendo los compromisos y las obligaciones legales con los clientes. También hay importantes restricciones sobre el visionado de datos de clientes y sistemas, además de sobre su manejo en varios entornos operativos. Los datos confidenciales y de los clientes no se transfieren fuera del entorno de producción sin la aprobación escrita del administrador de incidencias registrada en el tique de incidencia correspondiente. 

Microsoft comprueba que el riesgo para los clientes y negocios se ha contenido con éxito y que las medidas correctivas se han implementado. En caso necesario, se llevan a cabo pasos de atenuación de emergencia para resolver los riesgos de seguridad inmediatos asociados con el evento. 

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of the data processor service for Windows Enterprise routine audit cycle. 

## <a name="customer-notice"></a>Aviso al cliente

Microsoft data processor service for Windows Enterprise notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of the data processor service for Windows Enterprise. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached. 

After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances: 

 - Microsoft considera que el acto de realizar una notificación incrementará el riesgo para otros clientes. Por ejemplo, el acto de enviar una notificación puede alertar a un adversario e impedir una corrección adecuada. 
 - Otras circunstancias inusuales o extremas expuestas por el departamento legal de Microsoft, asuntos legales y externos corporativos (CELA), y el administrador de incidentes ejecutivo. 

 El servicio de tratamiento de datos de Microsoft para Windows Enterprise proporciona a los clientes información detallada, lo que les permite realizar investigaciones internas y satisfacer los compromisos contraídos con los usuarios finales sin retrasar indebidamente el proceso de notificación. 

La notificación de una infracción de datos personales se entregará al cliente por cualquier medio elegido por Microsoft, incluyendo el correo electrónico. La notificación de una infracción de datos se enviará a la lista de contactos de seguridad proporcionada en Azure Defender, que puede configurarse siguiendo las [directrices de implementación](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Si no se proporciona información de contacto en Azure Defender, la notificación se enviará a uno o varios administradores de una suscripción de Azure. Para asegurarse de que pueda entregarse la notificación correctamente, es responsabilidad del cliente proporcionar información de contacto administrativa correcta en cada suscripción y portal de servicios en línea aplicables.

El equipo del servicio de tratamiento de datos para Windows Enterprise también puede elegir enviar notificaciones a otros miembros del personal de Microsoft, como, por ejemplo, el servicio de atención al cliente, los administradores de cuentas de clientes o los administradores de cuentas técnicas. Por lo general, estas personas suelen tener relaciones estrechas con los clientes y pueden hacer que las correcciones se lleven a cabo más rápidamente. 

Para obtener más información sobre cómo Microsoft detecta y responde ante una vulneración de datos personales, vea [Notificación de vulneraciones de datos según el RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) en el Portal de confianza del servicio.
