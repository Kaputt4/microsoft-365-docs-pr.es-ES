---
title: Evaluar los riesgos de privacidad de datos e identificar los elementos confidenciales con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Determine las regulaciones de privacidad de datos, los escenarios relevantes, la preparación y los tipos de información confidencial que se encuentran en el entorno de Microsoft 365.
ms.openlocfilehash: f8d8fd0b5e6d8876dead566a50408cb2e7419386
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854357"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Evaluar los riesgos de privacidad de datos e identificar los elementos confidenciales con Microsoft 365

La evaluación de los riesgos y las regulaciones de privacidad de datos a los que está sujeta la organización es un primer paso clave antes de implementar las acciones de mejora relacionadas, incluidas las que se pueden conseguir con los servicios y características de Microsoft 365. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Regulaciones de privacidad de datos potencialmente aplicables

Para obtener una buena referencia sobre el marco normativo más amplio para las regulaciones de privacidad de datos, vea el [portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/) y la [serie de artículos sobre el Reglamento General del Reglamento de protección de datos (RGPD)](../compliance/gdpr.md), así como otros materiales de la normativa que puede estar sujeto a su sector o región.

### <a name="gdpr"></a>RGPD

La RGPD, la más conocida y que se menciona en la normativa sobre privacidad de los datos, regula la recopilación, el almacenamiento, el procesamiento y el uso compartido de los datos personales relacionados con una persona física identificada o identificable que es un residente de la Unión Europea (UE). 

Según el artículo 4 de RGPD: 

- «datos personales»: toda información relativa a una persona física identificada o identificable («interesado»); una persona física identificable es la que puede identificarse, directa o indirectamente, en particular por referencia a un identificador, como un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o varios factores específicos de la identidad física, fisiológica, genética, mental, económico, cultural o social de esa persona física.

### <a name="iso-27001"></a>ISO 27001

La adherencia a otros estándares como ISO 27001 también ha sido reconocida por varias autoridades de supervisión europeas como un proxy válido de propósito en el personal, el proceso y el espectro tecnológico. Los estándares que especifican la superposición y el cumplimiento de los mecanismos de protección basados en ISO-27001 pueden considerarse como un proxy que cumple algunas obligaciones de privacidad en determinadas circunstancias.

### <a name="other-data-privacy-regulations"></a>Otros reglamentos de privacidad de datos

Otras regulaciones de privacidad de datos destacadas también especifican los requisitos para el tratamiento de datos personales.

En los Estados Unidos, se incluye la ley de protección del consumidor de California ([CCPA](../compliance/ccpa-faq.md)), HIPAA-tecnología (Ley de privacidad de atención sanitaria de Estados Unidos) y la ley Graham Leach BLILEY (GLBA). Las regulaciones adicionales específicas del estado también son locales o en desarrollo. 

En todo el mundo, algunos ejemplos adicionales incluyen el Act de implementación de RGPD Nacional de Alemania (BDSG), la ley de protección de datos de Brasil (LGPD) y muchas otras.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Asignación del Reglamento a las categorías de controles técnicos de Microsoft 365

Muchas de las reglamentaciones relacionadas con la privacidad de datos tienen requisitos que se superponen, por lo que debe comprender a qué regulaciones están sujetas antes de desarrollar cualquier esquema de control técnico. 

Para obtener una referencia posterior en los artículos de esta solución general, esta tabla contiene fragmentos de un muestreo de las regulaciones de privacidad de datos. 

| Regulación | Artículo/sección | Toma | Categorías de controles técnicos aplicables |
|:-------|:-----|:-------|:-------|
| RGPD | Artículo 5, apartado 1, f | Los datos personales se procesarán de manera que garanticen la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida, destrucción o daños accidentales, utilizando las medidas técnicas o organizacionales adecuadas (integridad y confidencialidad).  |  Todos <br> Identidad <br> Dispositivo <br> Protección contra amenazas <br> Proteger la información <br> Controlar la información <br> Detectar y responder |
|  | Artículo (32) (1) (a) | Teniendo en cuenta el estado de la arte, los costes de la aplicación y la naturaleza, ámbito, contexto y propósito del tratamiento, así como el riesgo de la variación de la probabilidad y la gravedad de los derechos y libertades de las personas físicas, el responsable del tratamiento y el procesador deberán implementar las medidas técnicas y organizativas adecuadas para garantizar un nivel de seguridad adecuado al riesgo. , incluidas, entre otras cosas adecuadas: a, el seudonimización y cifrado de datos personales. | Proteger la información |
|  | Artículo (13) (2) (a) | "... en el momento en que se obtengan los datos personales, el responsable del tratamiento deberá proporcionar al interesado los datos siguientes con la siguiente información necesaria para garantizar el tratamiento equitativo y transparente: (a) el período durante el cual se almacenarán los datos personales, o si no es posible, los criterios empleados para determinar dicho período. | Controlar la información |
|  | Artículo (15) (1) (e) | El interesado tendrá derecho a obtener de la confirmación del responsable del tratamiento de si los datos personales que le conciernen o no están en proceso de tratamiento; y, en ese caso, el acceso a los datos personales y la siguiente información: (e) la existencia del derecho de solicitar a la rectificación del responsable del tratamiento o de la eliminación de datos personales o de la restricción del tratamiento de datos personales sobre el interesado o de un objeto a dicho tratamiento | Detectar y responder |
| LGPD | Artículo 46 | Los agentes de procesamiento deben adoptar medidas de seguridad, técnicas y administrativas capaces de proteger datos personales de accesos no autorizados y situaciones accidentales o ilícitas de destrucción, pérdida, alteración, comunicación o cualquier tipo de procesamiento incorrecto o ilegal. | Proteger la información <br> Controlar la información <br> Detectar y responder|
|  | Artículo 48 | El responsable debe comunicar a la autoridad nacional y al interesado todo incidente de seguridad que pueda dar lugar a riesgos o daños relevantes a los interesados. | Detectar y responder |
| HIPPA-ALTA TECNOLOGÍA | 45 CFR 164.312(e)(1) | Implementar medidas técnicas de seguridad para protegerse contra el acceso no autorizado a información de salud protegida electrónicamente que se transmite a través de una red de comunicaciones electrónicas. | Proteger la información |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementar un mecanismo para cifrar información de salud protegida electrónicamente cuando se considere necesario. | Proteger la información |
|  | 45 CFR 164.312(c)(2) | Implementar mecanismos electrónicos para corroborar que la información de salud protegida electrónicamente no se ha modificado o destruido de forma no autorizada. | Controlar la información |
|  | 45 CFR 164.316(b)(1)(i) | Si esta subparte requiere que se documente una acción, actividad o evaluación, mantenga un registro escrito (que puede ser electrónico) de la acción, actividad o evaluación. | Controlar la información |
|  | 45 CFR 164.316(b)(1)(ii) | Conservar la documentación exigida por el párrafo (b)(1) de esta sección durante 6 años a partir de la fecha de creación o la fecha en que fue efectiva por última vez, la que sea posterior. | Controlar la información |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementar procedimientos para revisar regularmente registros de la actividad del sistema de información, como registros de auditoría, informes de Access y informes de seguimiento de incidentes de seguridad | Detectar y responder |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identificar y responder a incidentes de seguridad sospechosos o conocidos; mitigar, en la medida de lo posible, efectos negativos de los incidentes de seguridad que se conozcan en la entidad cubierta o la empresa asociada y documentar incidencias de seguridad y sus resultados. | Detectar y responder |
|  | 45 C.F.R. 164.312(b) | Implemente mecanismos de hardware, software y procedimientos que registren y examinen la actividad en sistemas de información que contienen o usan información de salud protegida electrónica. | Detectar y responder |
| CCPA | 1798.105 (c) | Una empresa que recibe una solicitud verificable de un consumidor para eliminar la información personal del consumidor con arreglo a la subdivisión (a) de esta sección, eliminará la información personal del cliente de sus registros y dirigirá a todos los proveedores de servicios para que eliminen la información personal del cliente de sus registros. | Detectar y responder |
|  | 1798.105 (d) | (excepciones a 1798.105 (c) <br> No es necesario que un negocio o un proveedor de servicios cumplan la solicitud de un consumidor para eliminar la información personal del cliente si es necesario para que el proveedor de servicios o negocios mantenga la información personal del consumidor para: (consulte el Reglamento actual para obtener más información). | Detectar y responder |
|||||

>[!Important]
>No pretende ser una lista exhaustiva. Consulte [Administrador de cumplimiento](../compliance/compliance-manager-overview.md) o asesor legal o de cumplimiento para obtener más información sobre la aplicabilidad de las secciones citadas a las categorías de controles técnicos que aparecen en la lista.
>

## <a name="knowing-your-data"></a>Conocer los datos

Independientemente de los reglamentos a los que esté sujeto, los diferentes tipos de datos de usuario dentro y fuera de la organización que interactúan con los sistemas son factores importantes que pueden afectar a la estrategia general de protección de datos personales, sujeto a las regulaciones de la industria y del gobierno que se aplican a la organización. Esto incluye dónde se almacenan los datos personales, qué tipo de información es y qué parte de ellas hay y en qué circunstancias se recopilaron.
 
![Conocer los datos: Qué tipo es y qué parte de él es y en qué circunstancias se recopiló](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Portabilidad de los datos 

Los datos también se desplazan a lo largo del tiempo a medida que se procesan, se refinan y otras versiones se derivan de él. Una instantánea inicial nunca es suficiente. Debe haber un proceso continuo para conocer sus datos. Representa uno de los mayores retos para organizaciones de gran tamaño que manejan grandes cantidades de datos personales. Las organizaciones que no abordan el problema "Conozca sus datos" podrían acabar con un riesgo muy alto y posibles multas de las agencias regulatorias.

![Ciclo de vida de los datos](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Dónde se encuentra el dato personal

Para tratar las regulaciones de privacidad de datos, no puede confiar en nociones generales de dónde cree que pueden existir datos personales, ya sea ahora o en el futuro. Las regulaciones de privacidad de datos requieren que las organizaciones demuestren que saben donde los datos personales están de manera continua. Esto hace que sea importante tomar una instantánea inicial de todos los orígenes de datos para poder almacenar información personal, incluido el entorno 365 de Microsoft y establecer mecanismos para la supervisión y detección continuas.

Si aún no ha evaluado su disponibilidad general y los riesgos asociados con las regulaciones de privacidad de datos, use el siguiente marco de 3 pasos para empezar. 

>[!Note]
>Este artículo y su contenido no están destinados a tener en lugar los servicios de asesoría legal. Solo proporciona una guía básica y vínculos a herramientas que pueden ser de ayuda en las primeras etapas de la evaluación.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Paso 1: desarrolle un conocimiento básico de los escenarios de datos personales de su organización 

Debe evaluar la exposición al riesgo de privacidad de los datos en función del tipo de datos personales que administre actualmente, dónde se almacenan, qué controles de protección se colocan en él, cómo se administra el ciclo de vida y quién tiene acceso a él. 

Como punto de partida, es importante inventariar los tipos de datos personales que existen en el entorno de Microsoft 365. Use estas categorías:

- Datos de empleados necesarios para llevar a cabo las funciones empresariales cotidianas
- Datos que la organización tiene sobre sus clientes empresariales, asociados y otras relaciones en el escenario de negocio a negocio (B2B)
- Datos que la organización tiene sobre los consumidores que proporcionan información a los servicios en línea que la organización administra en el escenario de negocio a cliente (B2C)

A continuación, se muestra un ejemplo de los distintos tipos de datos para los departamentos típicos de una organización.

![Tipos de datos personales](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Gran parte de los datos personales sujetos a la normativa de privacidad de datos normalmente se recopilan y almacenan fuera de Microsoft 365. Es necesario que los datos personales de aplicaciones móviles o Web de consumo se hayan exportado desde dichas aplicaciones a Microsoft 365 para estar sujetos a los controles de privacidad de datos dentro de Microsoft 365. 

La exposición de privacidad de los datos en Microsoft 365 puede ser más limitada en relación con las aplicaciones web y los sistemas CRM, que esta solución no soluciona.

También es importante pensar en los siguientes desafíos comunes de cumplimiento de privacidad de datos al evaluar el perfil de riesgo:

 - **Distribución de datos personales.** ¿Cómo está disperso información sobre un tema determinado? ¿Se conoce bien para convencer a los organismos normativos de que se implementan los controles adecuados? ¿Se puede investigar y corregir si es necesario?
- **Protección contra la exfiltración.** ¿Cómo se protegen los datos personales de un determinado tipo o origen y cómo responder en caso de que se prodieron?
- **Protección frente a riesgo.** ¿Qué mecanismos de protección de la información son adecuados en relación con el riesgo y cómo mantener la continuidad del negocio y la productividad y minimizar el impacto del usuario final si se requiere la intervención del usuario final? Por ejemplo, ¿debe usarse la clasificación manual o el cifrado?
- **Retención de datos personales.** ¿Durante cuánto tiempo debe conservarse la información que contiene datos personales por razones empresariales válidas y cómo evitar pasadas de mantenimiento de ti permanente, con un equilibrio con las necesidades de retención de la continuidad del negocio?
- **Administrar solicitudes de interesados.** ¿Qué mecanismos se necesitarán para controlar las solicitudes de los interesados (interesado) y las acciones correctivas, como anonymization, censura y eliminación?
- **Supervisión y generación de informes en curso.** ¿Qué tipo de técnicas de supervisión, investigación y creación de informes de día a día están disponibles para los distintos tipos de datos y orígenes?
- **Limitaciones en el procesamiento de datos.** ¿Hay limitaciones en el uso de datos para la información recopilada o almacenada a través de estos métodos que la organización debe reflejar en los controles de privacidad? Por ejemplo, los compromisos que el personal de ventas no va a usar para los datos personales puede requerir que su organización ponga en marcha los mecanismos para evitar la transferencia o el almacenamiento de dicha información en sistemas asociados con la organización de ventas.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Datos de empleados necesarios para llevar a cabo las funciones empresariales cotidianas

Las organizaciones por naturaleza necesitan recopilar datos de los empleados para fines de identidad y de recursos humanos electrónicos, sujetos a lo que aceptan en sus contratos de empleados. Siempre que una persona trabaje para una compañía, esto no suele ser un problema. Es posible que la organización desee poner en marcha los mecanismos para evitar que los actores malintencionados puedan exfiltrar o perder datos personales de los empleados. 

Si una persona deja una compañía, las organizaciones suelen tener programaciones, procedimientos y programaciones de retención y eliminación para eliminar cuentas de usuario, retirar buzones y unidades personales y cambiar el estado de los empleados en aspectos como los sistemas de recursos humanos. En situaciones en las que interviene un litigio, un empleado u otra parte en una investigación legal puede tener motivos válidos para obtener información sobre los datos personales almacenados en los sistemas de la organización. En algunas ocasiones, es posible que esa parte solicite que se eliminen los datos o anonimizan. 

Para cubrir estas necesidades, las organizaciones deben tener procesos y procedimientos en el caso de que se desplacen las necesidades preventivas, de detectives y de medios para facilitar estas solicitudes, teniendo en cuenta que cierta información sobre un empleado puede considerarse razonablemente crucial para la continuidad del negocio. Por ejemplo, la información que un individuo ha creado un archivo o ha realizado una función. 

>[!Note]
>Para conocer las técnicas de investigación y corrección de datos personales en Microsoft 365, consulte el [artículo monitor y responder](information-protection-deploy-monitor-respond.md). Es posible que también desee emplear esquemas de protección y clasificación automatizados para asegurarse de que los datos personales se controlan dentro de la organización, así como evitar que abandonen la organización en situaciones de actor malintencionado. Consulte el [artículo proteger información](information-protection-deploy-protect-information.md) para obtener más información.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Datos que la organización tiene sobre sus clientes empresariales en el escenario B2B

La recopilación de información de B2B también es un reto porque es posible que su organización tenga que mantener registros de nombres de clientes y transacciones en sus diversos sistemas con fines de continuidad empresarial, pero proteger dicha información de la exfiltración accidental o malintencionada. Al igual que los datos de los empleados, las organizaciones deben tener implementadas directivas, procedimientos y controles técnicos para proteger dichos datos, así como caducar de acuerdo con las programaciones de retención y eliminación definidas. 

Por lo general, los contratos con clientes externos, asociados y las otras entidades con las que la organización tiene un idioma que se encarga de la administración de estos datos, incluida la protección, la retención y la eliminación, tanto durante y después de que la entidad tenga una relación con la organización. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Datos que la organización tiene sobre los consumidores que proporcionan información a los servicios en línea que administra la organización en el escenario B2C

Esta categoría es la que la mayoría de los usuarios opinan sobre la privacidad de los datos, debido a muchas instancias públicas de pérdida de datos de clientes. Esto puede ser intencionado, como un tercero con contrato para el proveedor, o involuntariamente, como la exfiltración por un actor malintencionado. La protección de datos de clientes es uno de los principales motivos por los que la UE y otros usuarios han promulgado estas regulaciones. Los reglamentos de privacidad de datos como RGPD y CCPA requieren la planeación para:

- [Planes de acción](../compliance/gdpr-action-plan.md) y [listas de comprobación de preparación de responsabilidad](../compliance/gdpr-arc-office365.md)
- [Evaluaciones del impacto en la protección de datos](../compliance/gdpr-data-protection-impact-assessments.md)
- [Notificaciones de incumplimiento](../compliance/gdpr-breach-office365.md)
- [Solicitudes de interesados](../compliance/gdpr-dsr-office365.md)

Si su organización no realiza muchas recopilaciones de datos de clientes directos, esta categoría puede ser menos importante. Sin embargo, es posible que tenga que seguir los procesos descritos en estos artículos para lograr el cumplimiento normativo.

### <a name="step-1-summary"></a>Resumen del paso 1

Comprender la exposición al riesgo y la privacidad de los datos es un primer paso importante que se basa en la comprensión básica de los escenarios de datos personales de su organización.

Si no tiene datos personales de los consumidores en su entorno de Microsoft 365 o se limita a determinadas partes del entorno y la necesidad de un control técnico se basa en la exposición de los datos de consumo, es posible que el control técnico solo tenga que usarse en partes de riesgo alto del entorno, no en todas las partes.

Aunque una recomendación de la organización externa o de un conjunto de control estándar, como la puntuación de cumplimiento en Microsoft 365, puede ayudar a informar a su estrategia de control, la elección de la implementación debe estar controlada por el reconocimiento del inventario de datos para cuantificar la exposición de riesgos real.

La mayoría de las organizaciones tendrán alguna exposición a uno de los escenarios anteriores. Es importante realizar un enfoque holístico de la evaluación.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Paso 2: evaluar la preparación para cumplir con las regulaciones de privacidad de datos

Aunque son específicas de RGPD, las preguntas que se plantean en la [herramienta gratuita Microsoft RGPD Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) proporcionan un buen punto de partida para comprender la disponibilidad general de la privacidad de los datos. 

Las organizaciones que están sujetas a otras regulaciones de privacidad de datos, como CCPA en Estados Unidos o LGPD de Brasil, también pueden beneficiarse del inventario de preparación de disponibilidad con el RGPD de esta herramienta.

La evaluación de RGPD consta de las siguientes secciones:

| | |
|:-------|:-----|
| Gobierno | <ol><li>¿Su Directiva de privacidad indica explícitamente qué información de datos se está procesando? </li><li>¿Se ejecutan de forma regular evaluaciones de impacto de privacidad (PIA)? </li><li> ¿Utiliza una herramienta para administrar la información personal (PI)? </li><li> ¿Tiene autoridad legal para realizar negocios con datos de PI en un individuo determinado? ¿Realiza un seguimiento de los datos de consentimiento? </li><li> ¿Realiza un seguimiento, la implementación y la administración de controles de auditoría? ¿Supervisa si hay pérdidas de datos? </li></ol>|
| Eliminación y notificación | <ol><li>¿Proporciona instrucciones explícitas sobre cómo se puede obtener acceso a los datos de los usuarios? </li><li> ¿Tiene procesos documentados en su ubicación para controlar el consentimiento de cancelación? </li><li> ¿Tiene un proceso de eliminación automatizado de datos? </li><li>   ¿Tiene un proceso para validar la identidad al participar con un cliente? </li></ol>|
| Mitigación de riesgos y seguridad de la información | <ol><li>¿Usa herramientas para analizar datos no estructurados? </li><li>¿Están actualizados todos los servidores y aprovecha los firewalls para protegerlos? </li><li>¿Ejecuta copias de seguridad regulares de los servidores? </li><li>¿Supervisa activamente la pérdida de datos? </li><li>¿Cifra sus datos en reposo y en transmisiones? </li></ol>|
| Administración de directivas | <ol><li>¿Cómo se administran las reglas corporativas de enlace (BCRs)? </li><li>¿Realiza un seguimiento de los datos de consentimiento? </li><li> En una escala de 1 a 5, 5 cubiertos completamente, ¿los contratos cubren las clasificaciones de datos y los requisitos de tratamiento? </li><li>¿Tiene y prueba con regularidad un plan de respuesta a incidentes? </li><li>¿Qué directiva usa para administrar el acceso? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Paso 3: identificar los tipos de información confidencial que se producen en el entorno de Microsoft 365. 

Este paso implica la identificación de los tipos de información confidencial que están sujetos a controles reguladores específicos, así como la ocurrencia de ellos en el entorno de Microsoft 365. 

La búsqueda de contenido en el entorno que contiene personal puede ser una tarea formidable, que antes implicaba una combinación de búsqueda de cumplimiento, eDiscovery, eDiscovery avanzado, DLP y auditoría. 

Con la nueva solución de **clasificación de datos** en el centro de administración de cumplimiento de Microsoft, esto resulta mucho más sencillo con la capacidad del [Explorador de contenido](../compliance/data-classification-content-explorer.md) , que funciona con los tipos de información confidencial integrados o personalizados, incluidos los relacionados con los datos personales.
 
### <a name="sensitive-information-types"></a>Tipos de información confidencial

El centro de administración de cumplimiento de Microsoft viene preconfigurado con más de 100 tipos de información confidencial, la mayoría de ellos relacionados con la identificación y ubicación de datos personales. Estos tipos de información confidencial integrados pueden ayudar a identificar y proteger los números de tarjetas de crédito, los números de cuentas bancarias, los números de pasaporte, etc., en función de los patrones definidos por una expresión regular (regex) o una función. Para obtener más información, consulte [Qué buscan los tipos de información confidencial](../compliance/what-the-sensitive-information-types-look-for.md).

Si necesita identificar y proteger un tipo de elementos confidenciales específicos de la organización o regional, como un formato personalizado para los identificadores de los empleados u otra información personal que no esté ya cubierta por un tipo de información confidencial integrada, puede crear un tipo personalizado de información confidencial con estos métodos: 

- PowerShell
- Reglas personalizadas con coincidencia de datos exacta (EDM)
- A través de la interfaz de usuario del administrador del centro de cumplimiento, resaltada en el [artículo usar la puntuación de cumplimiento y el administrador de cumplimiento](information-protection-deploy-compliance.md)

También puede personalizar un tipo de información confidencial integrado existente.

Consulte estos artículos para obtener más información:

- [Personalizar un tipo de información confidencial integrado](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Tipos de información confidencial personalizados](../compliance/custom-sensitive-info-types.md)
- [Crear un tipo de información confidencial personalizado en el Centro de seguridad y cumplimiento](../compliance/create-a-custom-sensitive-information-type.md)
- [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Explorador de contenido

Una herramienta importante que para determinar la ocurrencia de elementos confidenciales en su entorno es el nuevo [Explorador de contenido](../compliance/data-classification-content-explorer.md) en el centro de administración de cumplimiento de Microsoft 365. Se trata de una herramienta automatizada para el análisis inicial y continuo de toda la suscripción a Microsoft 365 para la ocurrencia de los tipos de información confidencial y la visualización de los resultados.
 
La nueva herramienta explorador de contenido le permite identificar rápidamente las ubicaciones de los elementos confidenciales de su entorno, mediante tipos de información confidencial integrados o personalizados. Esto puede implicar el establecimiento de un proceso y la responsabilidad asignada a la investigación regular de la presencia y ubicación de los elementos confidenciales.

Además de los otros pasos resaltados en este artículo, se proporciona un punto de partida para identificar la exposición de riesgos general, la preparación y la ubicación de los elementos confidenciales para protegerlos mediante la configuración y supervisión planificada de Microsoft 365. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Otros métodos para identificar datos personales en su entorno

Además del explorador de contenido, las organizaciones tienen acceso a la capacidad de búsqueda de contenido para generar búsquedas personalizadas para encontrar datos personales en su entorno, mediante criterios de búsqueda avanzados y filtros personalizados.

En [este artículo](../compliance/search-for-and-find-personal-data.md)se proporcionan instrucciones detalladas sobre el uso de la búsqueda de contenido para la detección de datos personales. La búsqueda de contenido y otras técnicas de detección también se exploran en [interesado para RGPD y CCPA](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs).

En el [artículo monitor and Respond](information-protection-deploy-monitor-respond.md)se proporcionan más información sobre técnicas de investigación y corrección de datos personales en Microsoft 365.
