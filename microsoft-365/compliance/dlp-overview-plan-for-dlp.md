---
title: Plan de prevención de pérdida de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Información general sobre el proceso de planeación para la prevención de pérdida de datos
ms.openlocfilehash: 84f1dc0426ba88f934c1d67d71f75364adeb4340
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583357"
---
# <a name="plan-for-data-loss-prevention-dlp"></a>Planear la prevención de pérdida de datos (DLP)

Cada organización planeará e implementará la prevención de pérdida de datos (DLP) de forma diferente, ya que las necesidades empresariales, los objetivos, los recursos y la situación de cada organización son únicas para ellos. Sin embargo, hay elementos que son comunes a todas las implementaciones de DLP correctas. En este artículo se presentan los procedimientos recomendados que usan las organizaciones en su planeación de DLP.

## <a name="multiple-starting-points"></a>Varios puntos iniciales

Muchas organizaciones deciden implementar DLP para cumplir con diversas normativas gubernamentales o del sector. Por ejemplo, el Reglamento general de protección de datos (RGPD) de la Unión Europea o la Ley de portabilidad y responsabilidad de seguros de salud (HIPAA) o la Ley de privacidad del consumidor de California (CCPA). También implementan la prevención de pérdida de datos para proteger su propiedad intelectual. Pero el lugar de inicio y el destino final del viaje DLP varían. 

Las organizaciones pueden iniciar su recorrido dlp:

- desde un enfoque de plataforma, como querer proteger la información en mensajes de chat y canal de Teams o en Windows 10 dispositivos
- saber qué información confidencial quieren priorizar la protección, como los registros de atención médica, e ir directamente a definir directivas para protegerla
- sin saber cuál es su información confidencial, dónde está y quién hace qué con ella para que comiencen con la detección y categorización y tomen un enfoque más metódico
- sin saber cuál es su información confidencial, dónde está, o quién hace lo que hace con ella, pero se moverán directamente a definir directivas y usarán esos resultados como punto de partida y, a continuación, refinarán sus directivas desde allí
- saber que necesitan implementar la pila completa Microsoft 365 Information Protection y, por lo tanto, tienen la intención de tomar un enfoque metódico y a largo plazo

Estos son solo algunos ejemplos de cómo los clientes pueden acercarse a DLP y no importa desde dónde empiece, Microsoft 365 DLP es lo suficientemente flexible como para dar cabida a varios tipos de recorridos de protección de la información desde el principio hasta una estrategia de prevención de pérdida de datos completamente realizada. 

## <a name="overview-of-planning-process"></a>Información general sobre el proceso de planeación

La [información sobre la prevención de pérdida de](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) datos presenta los tres aspectos diferentes del proceso de [planeación de DLP](dlp-learn-about-dlp.md#plan-for-dlp). Vamos a entrar en más detalles aquí en los elementos que son comunes a todos los planes DLP.

### <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Cuando se implementa, las directivas DLP se pueden aplicar en grandes partes de la organización. IT can't develop a broad ranging plan on their own without negative consequences. Debe identificar a las partes interesadas que pueden:

- describir las normativas, las leyes y los estándares de la industria a los que está sujeta su organización
- categorías de elementos confidenciales que se protegerán
- los procesos empresariales en los que se usan
- el comportamiento de riesgo que debe ser limitado
- priorizar qué datos deben protegerse primero en función de la confidencialidad de los elementos y el riesgo implicado
- esquema del proceso de revisión y corrección de eventos de coincidencia de directiva DLP 
 
En general, estas necesidades tienden a ser un 85 % de protección reglamentaria y de cumplimiento, y un 15 % de protección de la propiedad intelectual. Estas son algunas sugerencias sobre los roles que se deben incluir en el proceso de planeación:

- Responsables normativos y de cumplimiento
- Director de riesgos
- Responsables legales
- Agentes de seguridad y cumplimiento
- Propietarios empresariales de los elementos de datos
- Usuarios empresariales
- TI

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a>Describir las categorías de información confidencial que se protegerán

A continuación, las partes interesadas describen las categorías de información confidencial que se van a proteger y el proceso de negocio en el que se usan. Por ejemplo, Microsoft 365 DLP define estas categorías:

- Financiera 
- Información médica y de salud
- Privacidad
- Personalizado

Las partes interesadas pueden identificar la información confidencial como "Somos un procesador de datos, por lo que debemos implementar protecciones de privacidad en la información del interesado y la información financiera".

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a>Establecer objetivos y estrategia

Una vez que haya identificado a sus partes interesadas y sepa qué información confidencial necesita protección y dónde se usa, las partes interesadas pueden establecer sus objetivos de protección y TI puede desarrollar un plan de implementación. 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a>Establecer plan de implementación

El plan de implementación debe incluir:

- Asignación del estado inicial y el estado final deseado y los pasos para ir de uno a otro
- cómo abordará la detección de elementos confidenciales
- planeación de la directiva y el orden en que se implementarán
- cómo abordará los requisitos previos
- planeación de cómo se probarán primero las directivas antes de pasar a la aplicación
- cómo entrenará a los usuarios finales
- cómo probar y ajustar las directivas
- cómo revisará y actualizará su estrategia de prevención de pérdida de datos en función de los cambios normativos, legales, estándares de la industria o protección de propiedad intelectual y necesidades empresariales

#### <a name="map-out-path-from-start-to-desired-end-state"></a>Asignar ruta de acceso de inicio a estado final deseado

Documentar cómo la organización va a pasar de su estado inicial al estado final deseado es esencial para comunicarse con las partes interesadas y establecer el ámbito del proyecto. Este es un conjunto de pasos que se usan habitualmente para implementar DLP. Querrás más detalles que esto, pero puedes usarlo para enmarcar la ruta de adopción de DLP.

![gráfico que muestra el orden común para implementar DLP](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a>Detección de elementos confidenciales

Hay varias maneras de descubrir qué elementos confidenciales individuales están y dónde se encuentran. Es posible que tenga etiquetas de confidencialidad ya implementadas o que haya decidido implementar una directiva DLP amplia en todas las ubicaciones que solo detectan y auditan elementos. Para obtener más información, vea [Know your data](information-protection.md#know-your-data).

#### <a name="policy-planning"></a>Planeación de directivas

Al comenzar la adopción de DLP, puede usar estas preguntas para centrar los esfuerzos de diseño e implementación de directivas.

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a>¿Qué leyes, reglamentos y estándares del sector debe cumplir su organización?

Dado que muchas organizaciones llegan a DLP con el objetivo del cumplimiento normativo, responder a esta pregunta es un punto de partida natural para planear la implementación de DLP. Pero, como implementador de TI, probablemente no esté posicionado para responderlo. Debe ser contestada por el equipo legal y los ejecutivos empresariales. 
 
**Ejemplo** Su organización está sujeta a Reino Unido. regulaciones financieras.


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a>¿Qué elementos confidenciales tiene su organización que deben protegerse de las filtraciones?

Una vez que su organización sepa dónde se encuentra en términos de las necesidades de cumplimiento normativo, tendrá una idea de qué elementos confidenciales deben protegerse de las filtraciones y cómo desea priorizar la implementación de directivas para protegerlos. Esto le ayudará a elegir las plantillas de directiva DLP más adecuadas. Microsoft 365 incluye plantillas DLP preconfiguradas para Financial, Medical and health, Privacy y puede crear las suyas propias con la plantilla Personalizada. A medida que diseña y crea sus directivas DLP reales, conocer la respuesta a esta pregunta también le ayudará a elegir el tipo de [información confidencial adecuada.](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)

**Ejemplo** Para empezar rápidamente, debe elegir la plantilla de directiva, que incluye los tipos `U.K. Financial Data` de información confidencial , y `Credit Card Number` `EU Debit Card Number` `SWIFT Code` . 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a>¿Dónde están los elementos confidenciales y en qué procesos empresariales participan?

Los elementos que contienen información confidencial de las organizaciones se usan todos los días durante la actividad empresarial. Debe saber dónde pueden producirse instancias de esa información confidencial y en qué procesos empresariales se usan. Esto le ayudará a elegir las ubicaciones adecuadas a las que aplicar las directivas DLP. Microsoft 365 Las directivas DLP se aplican a las ubicaciones:

- Correo electrónico de Exchange
- Sitios de SharePoint
- Cuentas de OneDrive
- Mensajes de canales y chats de Teams
- Windows 10 Dispositivos
- Microsoft Cloud App Security
- Repositorios locales

**Ejemplo** Los auditores internos de su organización están rastreando un conjunto de números de tarjeta de crédito. Mantienen una hoja de cálculo de ellos en un sitio SharePoint seguro. Varios de los empleados hacen copias y las guardan en su sitio de OneDrive para la Empresa trabajo, que se sincroniza con su Windows 10 dispositivo. Uno de ellos pega una lista de 14 de ellos en un correo electrónico e intenta enviarlo a los auditores externos para su revisión. Desea aplicar la directiva al sitio de SharePoint seguro, todos los auditores internos OneDrive para la Empresa cuentas, sus dispositivos Windows 10 y Exchange correo electrónico.

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a>¿Cuál es la tolerancia de las organizaciones a las filtraciones?

Los distintos grupos de la organización pueden tener diferentes vistas sobre lo que es un nivel aceptable de pérdida de elementos confidenciales y lo que no es. Lograr la perfección de cero fugas puede tener un costo demasiado alto para la empresa.

**Ejemplo** El grupo de seguridad de su organización, junto con el equipo legal, sienten que no debe haber ningún uso compartido de números de tarjetas de crédito con nadie fuera de la organización e insisten en que no se produzca ninguna fuga. Pero, como parte de la revisión periódica de la actividad del número de tarjeta de crédito, los auditores internos deben compartir algunos números de tarjetas de crédito con auditores de terceros. Si su directiva DLP prohíbe todo uso compartido de números de tarjeta de crédito fuera de la organización, habrá una interrupción significativa del proceso empresarial y un costo agregado para mitigar la interrupción a fin de que los auditores internos completen su seguimiento. Este costo adicional es inaceptable para el liderazgo ejecutivo. Para resolver esto, debe haber una conversación interna para decidir un nivel aceptable de fuga. Una vez que se decida, la directiva puede proporcionar excepciones para que determinadas personas compartan la información o se puede aplicar en modo de solo auditoría.

#### <a name="planning-for-prerequisites"></a>Planeación de requisitos previos

Antes de poder supervisar algunas ubicaciones dlp, hay requisitos previos que deben cumplirse. Vea las **secciones Antes de comenzar** de:

- [Introducción al examinador de prevención de pérdida de datos en el entorno local (versión preliminar)](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md#before-you-begin)
- [Introducción a la extensión de cumplimiento de Microsoft (versión preliminar)](dlp-chrome-get-started.md#before-you-begin)
- [Usar directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft (versión preliminar)](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a>Implementación de directivas

Cuando crea directivas DLP, considere la posibilidad de implementarlas gradualmente para evaluar su impacto y probar su eficacia antes de aplicarlas completamente. Por ejemplo, no desea que una nueva directiva DLP bloquee de forma involuntara el acceso a miles de documentos o rompa un proceso empresarial existente.
  
Si está creando directivas DLP con un gran impacto potencial, se recomienda seguir esta secuencia:
  
1. **Inicie en modo de prueba sin sugerencias de directiva** y, a continuación, use los informes DLP para evaluar el impacto. Los informes DLP le sirven para ver el número, la ubicación, el tipo y la gravedad de las coincidencias de directivas. En función de los resultados, puede ajustar las directivas según sea necesario. En el modo de prueba, las directivas DLP no afectarán a la productividad de las personas que trabajan en su organización. Además, use esta fase para probar el flujo de trabajo para la revisión de eventos DLP y la corrección de problemas.
    
2. **Pasa al modo de** prueba con notificaciones y directivas Sugerencias para que puedas empezar a enseñar a los usuarios sobre las directivas de cumplimiento y prepararlas para las directivas que se van a aplicar. Es útil tener un vínculo a una página de directiva de organización que proporciona más detalles sobre la directiva en la sugerencia de directiva. En esta fase, también puede pedir a los usuarios que informen de falsos positivos para poder refinar aún más las directivas. Pase a esta fase una vez que tenga confianza en que los resultados de la aplicación de directiva coincidan con lo que las partes interesadas tenían en mente. 
    
3. **Comience el cumplimiento completo de las directivas** para que se apliquen las acciones en las reglas y se proteja el contenido. Continúe supervisando los informes DLP y los informes de incidentes o las notificaciones para asegurarse de que los resultados sean los deseados. 

    ![Opciones para usar el modo de prueba y activar la directiva](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    Puede desactivar una directiva DLP en cualquier momento, lo que afecta a todas las reglas de la directiva. No obstante, también es posible desactivar reglas individuales mediante el botón de alternancia de estado del editor de reglas.

    ![Opciones para desactivar una regla de una directiva](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    También puede cambiar la prioridad de varias reglas en una directiva. Para hacerlo, abra una directiva para editarla. En una fila de una regla, elija el signo de puntos suspensivos (**...**) y elija una opción, como **Bajar** o **Llevar al final**. 

    ![Establecer la prioridad de la regla](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a>Aprendizaje para el usuario final

Cuando se desencadena una directiva DLP, puede configurar las directivas para enviar notificaciones por correo electrónico y mostrar [sugerencias](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) de directiva para directivas DLP a administradores y usuarios finales. Aunque las directivas aún están en modo de prueba y antes de que se establezcan para aplicar una acción de bloqueo, las sugerencias de directivas son formas útiles de concienciar sobre comportamientos de riesgo en elementos confidenciales y formar a los usuarios para evitar esos comportamientos en el futuro.  

#### <a name="review-dlp-requirements-and-update-strategy"></a>Revisar los requisitos de DLP y la estrategia de actualización

Las normativas, las leyes y los estándares del sector a los que está sujeta su organización cambiarán con el tiempo y sus objetivos empresariales para DLP también lo harán. Asegúrese de incluir revisiones periódicas de todas estas áreas para que su organización se mantenga en cumplimiento y la implementación de DLP siga a la medida de sus necesidades empresariales.

## <a name="approaches-to-deployment"></a>Enfoques para la implementación

|Descripción de las necesidades empresariales del cliente  | enfoque  |
|---------|---------|
|**Contoso Bank** está en un sector altamente regulado y tiene muchos tipos diferentes de elementos confidenciales en muchas ubicaciones diferentes. </br> - sabe qué tipos de información confidencial son prioridad. </br> - debe minimizar la interrupción del negocio a medida que se van implantando las directivas. </br> - tiene recursos de TI y puede contratar expertos para ayudar a planear, diseñar la implementación </br> - tiene un contrato de soporte técnico premier con Microsoft| - Tómese el tiempo para comprender qué normativas deben cumplir y cómo van a cumplir. </br> -Tómese el tiempo para comprender el mejor valor conjunto de la pila Microsoft 365 Information Protection </br> - Desarrollar un esquema de etiquetado de confidencialidad para elementos prioritarios y aplicar </br> - Implicar a los propietarios de procesos empresariales </br>- Directivas de diseño y código, implementación en modo de prueba, formación de usuarios </br>- repetir|
|**TailSpin Toys** no sabe lo que tiene o dónde está, y tiene poca o ninguna profundidad de recursos. Usan Teams, OneDrive para la Empresa y Exchange extensamente.     |- Comience con directivas sencillas en las ubicaciones priorizadas. </br>- Supervisar lo que se identifica </br>- Aplicar etiquetas de confidencialidad en consecuencia </br>- Refinar directivas, entrenar a los usuarios       |
|**Fabrikam** es una pequeña startup que quiere proteger su propiedad intelectual y debe moverse rápidamente. Están dispuestos a dedicar algunos recursos, pero no pueden permitirse contratar expertos externos. </br>- Los elementos confidenciales están en Microsoft 365 OneDrive para la Empresa/SharePoint </br>- La adopción de OneDrive para la Empresa y SharePoint es lenta, los empleados y la sombra de IT usan DropBox y Google Drive para compartir o almacenar elementos </br>- Los empleados valoran la velocidad de trabajo en relación con la disciplina de protección de datos </br>- Cliente aplplió y compró los 18 empleados nuevos Windows 10 dispositivos     |- Aproveche la directiva DLP predeterminada en Teams </br>- Usar la configuración restringida de forma predeterminada para SharePoint elementos </br>- Implementar directivas que impidan el uso compartido externo </br>- Implementar directivas en ubicaciones priorizadas </br>- Implementar directivas en Windows 10 dispositivos </br>- Bloquear cargas en almacenamiento en la nube que no OneDrive para la Empresa de almacenamiento en la nube      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a>Consulte también
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
