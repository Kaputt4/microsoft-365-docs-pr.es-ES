---
title: Notificación de infracciones de datos según el RGPD
description: Se explica cómo Microsoft protege contra una vulneración de datos personales, y cómo responde y le notifica si se produce una vulneración.
keywords: Office 365, Microsoft 365, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
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
ms.openlocfilehash: ae69a8330f5daec275247e718f7eb66a5f0f8bf9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633445"
---
# <a name="breach-notification-under-the-gdpr"></a>Notificación de infracciones de datos según el RGPD

Como encargado del tratamiento, Office 365 garantizará que nuestros clientes cumplan con los requisitos de notificación de vulneraciones del RGPD como responsables de los datos. Con ese fin, nos comprometemos a lo siguiente:

- Proporcionar a los clientes la opción de especificar un contacto de privacidad específico que recibirá notificaciones en caso de que se produzcan infracciones. Los clientes podrán especificar este contacto en Azure Active Directory (AAD).
- Notificar a los clientes de las vulneraciones de datos personales en un plazo de 72 horas después de declararse la vulneración. La notificación se realizará por correo electrónico al contacto especificado por el cliente.
- En la notificación inicial se incluirá, como mínimo, una descripción de la naturaleza de la infracción, una aproximación del impacto en los usuarios y los pasos de mitigación (si corresponde). Si nuestra investigación no se completa en el momento de la notificación inicial, indicaremos los pasos siguientes y las escalas de tiempo para la comunicación posterior a la notificación inicial.

Microsoft reconoce que los responsables de los datos son responsables de realizar evaluaciones de riesgos y de determinar si es necesario notificar ante una vulneración al DPA del cliente; al notificar a los clientes, proporcionaremos la información necesaria para realizar una evaluación. Por lo tanto, Microsoft notificará a los clientes ante cualquier vulneración de datos personales, excepto en los casos en que se confirme que los datos personales son ininteligibles (por ejemplo, datos con un cifrado muy seguro donde se confirme la integridad de las claves).

## <a name="office-365-investments-in-data-security"></a>Inversiones de Office 365 en la seguridad de los datos

Además de nuestro compromiso para ofrecer una notificación puntual de las vulneraciones, Office 365 invierte ampliamente en sistemas, procesos y personal para reducir la probabilidad de que se produzcan vulneraciones de datos personales, y para detectar y mitigar rápidamente las consecuencias de una vulneración en caso de que se produzca.

Esta es una descripción de algunas de nuestras inversiones en este espacio:

- **Sistemas de control de acceso.** Office 365 mantiene una directiva de “cero acceso permanente”, lo que significa que los ingenieros no tienen acceso al servicio, excepto si se concede de forma explícita en respuesta a un incidente específico para el que se necesita acceso con elevación de privilegios. Cada vez que se conceda el acceso en virtud del principio del mínimo privilegio: los permisos concedidos para una solicitud específica solo permiten realizar un conjunto mínimo de acciones necesarias para completar esa solicitud. Para hacerlo, Office 365 mantiene una separación estricta entre “roles de elevación de privilegios”, donde cada rol solo tiene permiso para realizar acciones predefinidas específicas. El rol “Acceso a datos de clientes” es distinto de otros roles que suelen usarse con más frecuencia para administrar el servicio y, antes de su aprobación, se examina de forma muy exhaustiva. En conjunto, estas inversiones en el control de acceso reducen en gran medida la probabilidad de que un ingeniero de Office 365 obtenga acceso de forma inapropiada a los datos de clientes.

- **Automatización y sistemas de supervisión de la seguridad:** Office 365 mantiene sólidos sistemas de supervisión de la seguridad en tiempo real. Entre otros problemas, estos sistemas generan alertas de intentos de acceso ilegales a los datos de clientes, así como de intentos de transferencia de datos ilícita fuera de nuestro servicio. En relación con los puntos sobre el control de acceso mencionados anteriormente, nuestros sistemas de supervisión de la seguridad mantienen registros detallados de las solicitudes de elevación de privilegios que se solicitan y las acciones realizadas para las solicitudes de elevación de privilegios concedidas. Office 365 también mantiene inversiones de soluciones automáticas que actúan automáticamente para mitigar amenazas en respuesta a los problemas que detectamos, y equipos dedicados para responder ante alertas que no se puedan solucionar automáticamente. Para validar nuestros sistemas de supervisión de la seguridad, Office 365 realiza de forma periódica ejercicios de simulación de ataques, donde un equipo interno de pruebas de penetración simula el comportamiento de un atacante contra el entorno de producción. Estos ejercicios permiten implementar mejoras periódicas en nuestra capacidad de respuesta y supervisión de la seguridad.

- **Personal y procesos:** además de las acciones de automatización descritas anteriormente, Office 365 mantiene procesos y equipos responsables, tanto para proporcionar aprendizaje a toda la organización sobre procesos de administración de incidentes y de la privacidad, como para ejecutar esos procesos durante una infracción. Por ejemplo, se mantiene y comparte con los equipos de toda la organización un procedimiento operativo estándar ante infracciones de la privacidad. En este procedimiento operativo estándar, se describen en detalle los roles y las responsabilidades, tanto de los equipos individuales de Office 365, como de los equipos centralizados de respuesta ante incidentes de seguridad. Estos cubren lo que necesitan hacer los equipos para mejorar su propia posición de seguridad (realizar revisiones de seguridad, integración con sistemas centralizados de supervisión de la seguridad y otros procedimientos recomendados), así como lo que los equipos tendrían que hacer en caso de una infracción real (escalación rápida para dar respuesta ante incidentes, mantener y proporcionar orígenes de datos específicos que se usarán para agilizar el proceso de respuesta). Además, los equipos reciben aprendizaje de forma periódica sobre clasificación de datos, y se corrigen los procedimientos de almacenamiento y procesamiento de datos personales.

El punto de referencia más importante es que Office 365 invierte en gran medida en reducir la probabilidad y las consecuencias de vulneraciones de datos personales que afecten a nuestros clientes. Si se produce una vulneración de datos personales, nos comprometemos a notificar rápidamente a nuestros clientes cuando se confirme esa vulneración.

## <a name="what-to-expect-in-the-event-of-breach"></a>Expectativas en caso de una infracción

En la sección anterior, se describen las inversiones que realiza Office 365 para reducir la probabilidad de que se produzcan infracciones de datos. En el caso improbable de que se produzca una infracción, los clientes recibirán una experiencia predecible en términos de lo siguiente:

- Ciclo de vida de respuesta ante incidentes coherente en Office 365. Como se describió anteriormente, Office 365 mantiene procedimientos operativos estándar detallados de respuesta ante incidentes, donde se describen cómo tienen que prepararse los equipos ante una vulneración y cómo necesitan actuar en caso de que se produzca una vulneración. Esto garantiza que nuestras protecciones y procesos se aplican en todo el servicio.

- Criterios coherentes para notificar a los clientes. Nuestros criterios de notificación se centran en la confidencialidad, la integridad y la disponibilidad de los datos de clientes. Office 365 notificará directamente a los clientes en caso de que se produzcan problemas que afecten a la confidencialidad o la integridad de los datos de clientes. Es decir, notificaremos a los clientes si se obtiene acceso a sus datos sin la autorización correcta, o si se produce una destrucción o pérdida de datos inadecuadas. Office 365 también informará de problemas que afecten a la disponibilidad de los datos, aunque esto suele realizarse con el Panel de estado del servicio.

- Detalles de notificaciones coherentes. Cuando Office 365 envíe comunicaciones relacionadas con infracciones de datos, los clientes pueden recibirán detalles específicos; como mínimo, proporcionaremos los datos siguientes:

    - Momento de la infracción y momento en que se detectó la infracción.
    - El número aproximado de usuarios afectados.
    - El tipo de datos de usuario a los que se obtuvo acceso con la infracción.
    - Acciones necesarias para mitigar la vulneración, ya sea por el controlador o por el encargado.

Los clientes también necesitan tener en cuenta que Office 365, como encargado del tratamiento, no determinará el riesgo de una vulneración de datos. Si se detecta una vulneración de datos personales, notificaremos a nuestros clientes y les proporcionaremos los datos que necesiten para determinar de forma precisa el riesgo para los usuarios afectados y decidir si es necesario informar a las autoridades competentes. Para esa finalidad, se espera que los responsables de los datos determinen lo siguiente:

- Gravedad de la vulneración (es decir, determinación de los riesgos).
- Si es necesario notificar a los usuarios finales.
- Si es necesario notificar a las autoridades competentes.
- Pasos específicos que realizará el controlador para mitigar las consecuencias de la vulneración.

## <a name="contacting-microsoft"></a>Ponerse en contacto con Microsoft

En algunos escenarios, es posible que un cliente sea consciente de una infracción y puede que quiera notificar a Microsoft. El protocolo actual es que los clientes notifiquen al soporte técnico de Microsoft, que se pondrá en contacto con los equipos de ingeniería para obtener más información. En este escenario, los equipos de ingeniería de Microsoft se comprometen de igual manera a proporcionar rápidamente la información que necesiten los clientes mediante su contacto de soporte técnico.

## <a name="call-to-action-for-customers"></a>Llamada a la acción de los clientes

Como se indicó anteriormente, Office 365 se compromete a notificar a los clientes en un plazo de 72 horas desde la declaración de la vulneración. Se notificará al administrador de espacios empresariales del cliente. Además, Office 365 recomienda que los clientes designen un alias de contacto de privacidad global, lo que pueden hacer en el portal de Azure Active Directory (AAD). En el caso de que se produzca una vulneración de datos personales, se puede enviar un correo electrónico a este alias, además de la notificación que se enviará a los administradores.

El contacto de privacidad del cliente puede ser una persona de la organización, una lista de distribución o alguien que sea completamente externo a la organización. Office 365 solo pide a los clientes que especifiquen una dirección de correo electrónico para ese contacto, y los clientes pueden especificar esto en el portal de AAD, en el campo “Contacto de privacidad global”. Tenga en cuenta que este campo está relacionado, pero es distinto, del campo “Contacto técnico” en AAD. Si los clientes deciden especificar una lista de distribución para este contacto, necesitan asegurarse de que la lista de distribución esté configurada para permitir la recepción de mensajes de remitentes externos.

En resumen, Office 365 pide a los clientes que sigan este procedimiento para recibir las ventajas de nuestros procesos de notificación de infracciones:

- Decidir un contacto para recibir notificaciones por correo electrónico relacionadas con vulneraciones de datos personales. Este contacto tiene que conocer los requisitos del responsable en virtud del RGPD y necesita estar preparado para ponerse en contacto con el encargado del tratamiento de la organización y, posiblemente, con la DPA poco después de recibir la notificación. Los administradores de espacios empresariales también recibirán notificaciones de vulneraciones y, de forma similar, necesitan conocer los requisitos del responsable en virtud del RGPD.
- Especifique la dirección de correo electrónico del contacto de privacidad en el portal de AAD. Si no se proporciona información sobre el contacto de privacidad global, Microsoft solo notificará al administrador de espacios empresariales.
