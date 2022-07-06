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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Introducción al proceso de planeación para la prevención de pérdida de datos
ms.openlocfilehash: afda017b2cc627876134888a83f70e9464aba2c8
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634453"
---
# <a name="plan-for-data-loss-prevention-dlp"></a>Planear la prevención de pérdida de datos (DLP)

Todas las organizaciones planean e implementan la prevención de pérdida de datos de forma diferente, ya que las necesidades empresariales, los objetivos, los recursos y la situación de cada una son únicos. Sin embargo, hay elementos que son comunes a todas las implementaciones de DLP correctas. En este artículo se presentan los procedimientos recomendados que usan las organizaciones en su planeación DLP.

## <a name="multiple-starting-points"></a>Varios puntos de partida

Muchas organizaciones optan por implementar DLP para cumplir con diversas regulaciones gubernamentales o del sector. Por ejemplo, el Reglamento General de Protección de Datos (RGPD) de la Unión Europea, la Ley de Portabilidad y Responsabilidad de Seguros De Salud (HIPAA) o la Ley de Privacidad del Consumidor de California (CCPA). También implementan la prevención de pérdida de datos para proteger su propiedad intelectual. Sin embargo, el lugar de inicio y el destino final del recorrido DLP varían. 

Las organizaciones pueden iniciar su recorrido DLP:

- desde un enfoque de plataforma, como querer proteger la información en mensajes de chat y canales de Teams o en dispositivos Windows 10
- saber qué información confidencial quieren priorizar la protección, como los registros de atención médica, y ir directamente a definir directivas para protegerla
- sin saber cuál es su información confidencial, dónde está y quién está haciendo lo que con ella para que comiencen con la detección y categorización y adopten un enfoque más metódico
- sin saber cuál es su información confidencial, dónde está o quién está haciendo lo que con ella, pero se moverán directamente a la definición de directivas y usarán esos resultados como un lugar de partida y luego refinarán sus directivas desde allí.
- saber que necesitan implementar la pila de Microsoft Purview Information Protection completa y, por lo tanto, pretenden adoptar un enfoque metódico a más largo plazo

Estos son solo algunos ejemplos de cómo los clientes pueden acercarse a DLP y no importa desde dónde empiece, DLP es lo suficientemente flexible como para dar cabida a varios tipos de recorridos de protección de la información desde el principio hasta una estrategia de prevención de pérdida de datos totalmente realizada. 

## <a name="overview-of-planning-process"></a>Introducción al proceso de planeación

[En Learn about Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) se presentan los tres aspectos diferentes del [proceso de planeación DLP](dlp-learn-about-dlp.md#plan-for-dlp). Veremos más detalles aquí sobre los elementos que son comunes a todos los planes DLP.

### <a name="identify-stakeholders"></a>Identificación de las partes interesadas

Cuando se implementa, las directivas DLP se pueden aplicar en grandes partes de la organización. El equipo de TI no puede desarrollar un plan de amplia gama por sí mismo sin consecuencias negativas. Debe identificar a las partes interesadas que pueden:

- describir las regulaciones, las leyes y los estándares del sector a los que está sujeta su organización
- las categorías de elementos confidenciales que se van a proteger
- los procesos empresariales en los que se usan
- el comportamiento de riesgo que debe limitarse
- priorizar qué datos deben protegerse primero en función de la confidencialidad de los elementos y el riesgo implicados
- describir el proceso de revisión y corrección de eventos de coincidencia de directiva DLP 
 
En general, estas necesidades tienden a ser un 85 % de protección normativa y de cumplimiento y un 15 % de protección de la propiedad intelectual. Estas son algunas sugerencias sobre los roles que se van a incluir en el proceso de planeamiento:

- Oficiales de cumplimiento y reglamentación
- Director de riesgos
- Oficiales legales
- Agentes de seguridad y cumplimiento
- Propietarios empresariales de los elementos de datos
- Usuarios empresariales
- TI

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a>Describir las categorías de información confidencial que se van a proteger

A continuación, las partes interesadas describen las categorías de información confidencial que se van a proteger y el proceso empresarial en el que se usan. Por ejemplo, DLP define estas categorías:

- Financiera 
- Información médica y de salud
- Privacidad
- Personalizado

Las partes interesadas podrían identificar la información confidencial como "Somos un procesador de datos, por lo que tenemos que implementar protecciones de privacidad sobre la información del interesado y la información financiera".

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a>Establecer objetivos y estrategias

Una vez que haya identificado a las partes interesadas y sepa qué información confidencial necesita protección y dónde se usa, las partes interesadas pueden establecer sus objetivos de protección y TI puede desarrollar un plan de implementación. 


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

- Asignación del estado inicial y el estado final deseado y los pasos para pasar de uno a otro
- cómo abordará la detección de elementos confidenciales
- planificación de directivas y el orden en que se implementarán
- cómo abordará los requisitos previos
- planear cómo se probarán por primera vez las directivas antes de pasar a la aplicación
- cómo entrenará a los usuarios finales
- cómo probará y ajustará las directivas
- cómo revisará y actualizará su estrategia de prevención de pérdida de datos en función de los cambios normativos, legales, estándar del sector o protección de la propiedad intelectual y las necesidades empresariales

#### <a name="map-out-path-from-start-to-desired-end-state"></a>Asignación de la ruta de acceso desde el inicio hasta el estado final deseado

Documentar cómo va a obtener su organización desde su estado inicial hasta el estado final deseado es esencial para comunicarse con las partes interesadas y establecer el ámbito del proyecto. Este es un conjunto de pasos que se usan normalmente para implementar DLP. Querrá más detalles que esto, pero puede usarlo para enmarcar la ruta de adopción dlp.

![gráfico que muestra el orden común para implementar DLP.](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a>Detección de elementos confidenciales

Hay varias maneras de descubrir qué son los elementos confidenciales individuales y dónde se encuentran. Es posible que ya tenga etiquetas de confidencialidad implementadas o que haya decidido implementar una directiva DLP amplia en todas las ubicaciones que solo detectan y auditan elementos. Para obtener más información, consulte [Conocer los datos](information-protection.md#know-your-data).

#### <a name="policy-planning"></a>Planeamiento de directivas

Al comenzar la adopción de DLP, puede usar estas preguntas para centrar los esfuerzos de diseño e implementación de directivas.

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a>¿Qué leyes, reglamentos y estándares del sector debe cumplir su organización?

Dado que muchas organizaciones llegan a DLP con el objetivo de cumplimiento normativo, responder a esta pregunta es un punto de partida natural para planear la implementación de DLP. Sin embargo, como implementador de TI, probablemente no esté en posición de responder a ella. Debe ser respondido por su equipo legal y ejecutivos de negocios. 
 
**Ejemplo** Su organización está sujeta al Reino Unido. regulaciones financieras.


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a>¿Qué elementos confidenciales tiene su organización que deben protegerse contra fugas?

Una vez que su organización sepa dónde se encuentra en términos de necesidades de cumplimiento normativo, tendrá alguna idea de qué elementos confidenciales deben protegerse frente a fugas y cómo desea priorizar la implementación de directivas para protegerlos. Esto le ayudará a elegir las plantillas de directiva DLP más adecuadas. Microsoft Purview incluye plantillas DLP preconfiguradas para finanzas, médicos y de salud, privacidad y puede crear las suyas propias mediante la plantilla Personalizada. A medida que diseñe y cree las directivas DLP reales, conocer la respuesta a esta pregunta también le ayudará a elegir el [tipo de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types) adecuado.

**Ejemplo** Para empezar a trabajar rápidamente, elija la `U.K. Financial Data` plantilla de directiva, que incluye los `Credit Card Number`tipos de información confidencial , `EU Debit Card Number`y `SWIFT Code` . 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a>¿Dónde están los elementos confidenciales y en qué procesos empresariales participan?

Los elementos que contienen información confidencial de las organizaciones se usan todos los días en el curso de la actividad empresarial. Debe saber dónde pueden producirse las instancias de esa información confidencial y en qué procesos empresariales se usan. Esto le ayudará a elegir las ubicaciones adecuadas a las que aplicar las directivas DLP. Las directivas DLP se aplican a las ubicaciones:

- Correo electrónico de Exchange
- Sitios de SharePoint
- Cuentas de OneDrive
- Mensajes de canales y chats de Teams
- dispositivos Windows 10
- Microsoft Defender for Cloud Apps
- Repositorios locales

**Ejemplo** Los auditores internos de las organizaciones están realizando un seguimiento de un conjunto de números de tarjeta de crédito. Mantienen una hoja de cálculo de ellos en un sitio seguro de SharePoint. Varios de los empleados realizan copias y las guardan en su sitio de trabajo OneDrive para la Empresa, que se sincroniza con su dispositivo Windows 10. Uno de ellos pega una lista de 14 de ellos en un correo electrónico e intenta enviarlo a los auditores externos para su revisión. Querrá aplicar la directiva al sitio seguro de SharePoint, a todos los auditores internos OneDrive para la Empresa cuentas, a sus dispositivos Windows 10 y al correo electrónico de Exchange.

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a>¿Cuál es la tolerancia de las organizaciones a la fuga?

Los distintos grupos de su organización pueden tener diferentes vistas sobre qué es un nivel aceptable de pérdida de elementos confidenciales y qué no. Lograr la perfección de la fuga cero puede suponer un costo demasiado alto para el negocio.

**Ejemplo** El grupo de seguridad de las organizaciones, junto con el equipo legal, sienten que no debe haber ningún uso compartido de números de tarjeta de crédito con nadie fuera de la organización e insisten en que no haya pérdidas. Sin embargo, como parte de la revisión periódica de la actividad de número de tarjeta de crédito, los auditores internos deben compartir algunos números de tarjeta de crédito con auditores de terceros. Si la directiva DLP prohíbe el uso compartido de números de tarjeta de crédito fuera de la organización, habrá una interrupción significativa del proceso empresarial y un costo adicional para mitigar la interrupción para que los auditores internos completen su seguimiento. Este costo adicional es inaceptable para la dirección ejecutiva. Para resolver esto, debe haber una conversación interna para decidir un nivel aceptable de fuga. Una vez que se decida, la directiva puede proporcionar excepciones para que determinados usuarios compartan la información o se puede aplicar solo en modo de auditoría.

#### <a name="planning-for-prerequisites"></a>Planeamiento de requisitos previos

Para poder supervisar algunas ubicaciones DLP, se deben cumplir los requisitos previos. Consulte las secciones **Antes de comenzar** de:

- [Introducción al examinador de prevención de pérdida de datos en el entorno local (versión preliminar)](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md#before-you-begin)
- [Introducción a la extensión de cumplimiento de Microsoft](dlp-chrome-get-started.md#before-you-begin)
- [Uso de directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft (versión preliminar)](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a>Implementación de directivas

Cuando crea directivas DLP, considere la posibilidad de implementarlas gradualmente para evaluar su impacto y probar su eficacia antes de aplicarlas completamente. Por ejemplo, no quiere que una nueva directiva DLP bloquee involuntariamente el acceso a miles de documentos o interrumpa un proceso empresarial existente.
  
Si está creando directivas DLP con un gran impacto potencial, se recomienda seguir esta secuencia:
  
1. **Inicie en modo de prueba sin sugerencias de directiva** y, a continuación, use los informes DLP para evaluar el impacto. Los informes DLP le sirven para ver el número, la ubicación, el tipo y la gravedad de las coincidencias de directivas. En función de los resultados, puede ajustar las directivas según sea necesario. En el modo de prueba, las directivas DLP no afectarán a la productividad de las personas que trabajan en su organización. Además, use esta fase para probar el flujo de trabajo para la revisión de eventos DLP y la corrección de problemas.
    
2. **Vaya al modo de prueba con notificaciones y sugerencias de directiva** para que pueda empezar a enseñar a los usuarios sobre las directivas de cumplimiento y prepararlas para las directivas que se van a aplicar. Es útil tener un vínculo a una página de directiva de organización que proporcione más detalles sobre la directiva en la sugerencia de directiva. En esta fase, también puede pedir a los usuarios que notifiquen falsos positivos para poder refinar aún más las directivas. Pase a esta fase una vez que tenga la confianza de que los resultados de la aplicación de directiva coinciden con lo que tenían en mente las partes interesadas. 
    
3. **Comience el cumplimiento completo de las directivas** para que se apliquen las acciones en las reglas y se proteja el contenido. Continúe supervisando los informes DLP y los informes de incidentes o las notificaciones para asegurarse de que los resultados sean los deseados. 

    ![Opciones para usar el modo de prueba y activar la directiva.](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    Puede desactivar una directiva DLP en cualquier momento, lo que afecta a todas las reglas de la directiva. No obstante, también es posible desactivar reglas individuales mediante el botón de alternancia de estado del editor de reglas.

    ![Opciones para desactivar una regla en una directiva.](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    También puede cambiar la prioridad de varias reglas en una directiva. Para hacerlo, abra una directiva para editarla. En una fila de una regla, elija el signo de puntos suspensivos (**...**) y elija una opción, como **Bajar** o **Llevar al final**. 

    ![Establezca la prioridad de la regla.](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a>Entrenamiento del usuario final

Cuando se desencadena una directiva DLP, puede configurar las [directivas para enviar notificaciones por correo electrónico y mostrar sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) a administradores y usuarios finales. Aunque las directivas siguen en modo de prueba y antes de que se establezcan para aplicar una acción de bloqueo, las sugerencias de directiva son formas útiles de concienciar sobre los comportamientos de riesgo en elementos confidenciales y entrenar a los usuarios para evitar esos comportamientos en el futuro.  

#### <a name="review-dlp-requirements-and-update-strategy"></a>Revisión de los requisitos de DLP y la estrategia de actualización

Las regulaciones, las leyes y los estándares del sector a los que está sujeta su organización cambiarán con el tiempo y sus objetivos empresariales para DLP también. Asegúrese de incluir revisiones periódicas de todas estas áreas para que su organización se mantenga en cumplimiento y la implementación de DLP siga respondiendo a sus necesidades empresariales.

## <a name="approaches-to-deployment"></a>Enfoques para la implementación

|Descripción de las necesidades empresariales del cliente  | Enfoque  |
|---------|---------|
|**Contoso Bank** está en un sector altamente regulado y tiene muchos tipos diferentes de elementos confidenciales en muchas ubicaciones diferentes. </br> : sabe qué tipos de información confidencial son de máxima prioridad. </br> : debe minimizar la interrupción empresarial a medida que se implementan las directivas. </br> : tiene recursos de TI y puede contratar expertos para ayudar a planear, diseñar la implementación </br> : tiene un contrato de soporte técnico premier con Microsoft| - Tómese el tiempo para comprender qué normativas deben cumplir y cómo van a cumplir. </br> -Tómese el tiempo necesario para comprender mejor el valor conjunto de la pila de Microsoft Purview Information Protection </br> - Desarrollar un esquema de etiquetado de confidencialidad para los elementos prioritarios y aplicar </br> - Implicar a los propietarios de procesos empresariales </br>- Directivas de diseño y código, implementación en modo de prueba, entrenamiento de usuarios </br>- repetir|
|**TailSpin Toys** no sabe qué tienen o dónde está, y tienen poca o ninguna profundidad de recursos. Usan Teams, OneDrive para la Empresa y Exchange ampliamente.     |- Comience con directivas sencillas en las ubicaciones prioritarias. </br>- Supervisión de lo que se identifica </br>- Aplicar etiquetas de confidencialidad en consecuencia </br>- Refinar directivas, entrenar usuarios       |
|**Fabrikam** es una pequeña startup y quiere proteger su propiedad intelectual, y debe moverse rápidamente. Están dispuestos a dedicar algunos recursos, pero no pueden permitirse contratar expertos externos. </br>- Todos los elementos confidenciales están en Microsoft 365 OneDrive para la Empresa/SharePoint </br>- La adopción de OneDrive para la Empresa y SharePoint es lenta, los empleados/shadow IT usan DropBox y google drive para compartir o almacenar elementos </br>- Los empleados valoran la velocidad del trabajo sobre la materia de protección de datos </br>- El cliente se aplurgó y compró los 18 empleados nuevos dispositivos Windows 10     |- Aprovechar la directiva DLP predeterminada en Teams </br>- Usar la opción restringida de forma predeterminada para elementos de SharePoint </br>- Implementación de directivas que impiden el uso compartido externo </br>- Implementación de directivas en ubicaciones con prioridad </br>- Implementar directivas en dispositivos Windows 10 </br>- Bloquear cargas en almacenamiento en la nube que no es OneDrive para la Empresa      |

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

## <a name="see-also"></a>Vea también
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
