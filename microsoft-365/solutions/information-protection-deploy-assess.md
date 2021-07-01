---
title: Evaluar los riesgos de privacidad de datos e identificar elementos confidenciales con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Determine las normativas de privacidad de datos, los escenarios relevantes, la preparación y los tipos de información confidencial que se encuentran en su Microsoft 365 datos.
ms.openlocfilehash: 8e41dccea3569573d45b2e07e8ab7f122c44b311
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229316"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Evaluar los riesgos de privacidad de datos e identificar elementos confidenciales con Microsoft 365

Evaluar los riesgos y regulaciones de privacidad de datos a los que está sujeta su organización es un primer paso clave antes de implementar cualquier acción de mejora relacionada, incluidas las que se pueden lograr con Microsoft 365 características y servicios.

## <a name="potentially-applicable-data-privacy-regulations"></a>Normativas de privacidad de datos potencialmente aplicables

Para obtener una buena referencia sobre el marco normativo más amplio para las normativas de privacidad de datos, vea [el Portal](https://servicetrust.microsoft.com/) de confianza de servicios de Microsoft y la serie de artículos sobre el reglamento del Reglamento general de protección de datos [(RGPD),](/compliance/regulatory/gdpr)así como otros materiales sobre las normativas a las que puede estar sujeto en su industria o región.

### <a name="gdpr"></a>RGPD

El RGPD, el más conocido y citado de las normativas de privacidad de datos, regula la recopilación, el almacenamiento, el procesamiento y el uso compartido de los datos personales relacionados con una persona física identificada o identificable que sea residente de la Unión Europea (UE).

Según el artículo 4 del RGPD:

- "datos personales": cualquier información relacionada con una persona física identificada o identificable ('interesado'); una persona física identificable es aquella que puede identificarse, directa o indirectamente, en particular por referencia a un identificador como un nombre, un número de identificación, datos de ubicación, un identificador en línea o a uno o varios factores específicos de la identidad física, fisiológica, genética, mental, económica, cultural o social de esa persona física.

### <a name="iso-27001"></a>ISO 27001

El cumplimiento de otros estándares como ISO 27001 también ha sido reconocido por varias autoridades de supervisión europeas como un proxy válido de intenciones en todo el espectro de personas, procesos y tecnología. Los estándares que especifica la superposición y el cumplimiento de los mecanismos de protección basados en ISO-27001 pueden considerarse un proxy que cumple algunas obligaciones de privacidad en determinadas circunstancias.

### <a name="other-data-privacy-regulations"></a>Otras normativas de privacidad de datos

Otras normativas de privacidad de datos destacadas también especifican requisitos para el tratamiento de datos personales.

En los Estados Unidos, se incluyen la Ley de protección del consumidor de California[(CCPA),](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (ley de privacidad de cuidado de la salud de los Estados Unidos) y la Ley de Bliley de Graham Leach (GLBA). Las normativas adicionales específicas del estado también están en vigor o en desarrollo.

En todo el mundo, ejemplos adicionales incluyen la Ley de implementación del RGPD nacional de Alemania (BDSG), la Ley de protección de datos de Brasil (LGPD) y muchos otros.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Asignación de reglamentación Microsoft 365 categorías de control técnico

Muchas de las normativas relacionadas con la privacidad de datos tienen requisitos superpuestos, por lo que debe comprender a qué normativas están sujetas antes de desarrollar cualquier esquema de control técnico.

Para referencia posterior en los artículos de esta solución general, esta tabla proporciona extractos de un muestreo de las normativas de privacidad de datos.

| Reglamento | Artículo o sección | Extracto | Categorías de control técnico aplicables |
|:-------|:-----|:-------|:-------|
| RGPD | Artículo 5(1)(f) | Los datos personales se procesarán de manera que se garantice la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra pérdidas, destrucción o daños accidentales, mediante las medidas técnicas o organizativas apropiadas ("integridad y confidencialidad".  |  (Todos) <br> Identidad <br> Dispositivo <br> Protección contra amenazas <br> Protección de la información <br> Gobernanza de la información <br> Detección y respuesta |
|  | Artículo (32)(1)(a) | Teniendo en cuenta el estado de la técnica, los costos de implementación y la naturaleza, el ámbito, el contexto y los fines del procesamiento, así como el riesgo de que la probabilidad y la gravedad de los derechos y libertades de las personas físicas varían, el responsable del tratamiento y el encargado implementarán las medidas técnicas y organizativas adecuadas para garantizar un nivel de seguridad adecuado para el riesgo. , incluyendo, entre otras cosas, según corresponda: (a) la seudónimo y el cifrado de datos personales. | Protección de la información |
|  | Artículo (13)(2)(a) | "... el responsable del tratamiento, en el momento en que se obtengan los datos personales, proporcionará al interesado la siguiente información adicional necesaria para garantizar un procesamiento justo y transparente: (a) el período durante el cual se almacenarán los datos personales o, si no es posible, los criterios usados para determinar dicho período. | Gobernanza de la información |
|  | Artículo (15)(1)(e) | El interesado tendrá derecho a obtener de la confirmación del responsable del tratamiento si se están procesando o no los datos personales que le conciernen y, en ese caso, el acceso a los datos personales y la siguiente información: (e) la existencia del derecho a solicitar al responsable rectificar o eliminar datos personales o restringir el tratamiento de datos personales relativos al interesado o a oponerse a dichos datos. procesamiento | Detección y respuesta |
| LGPD | Artículo 46 | Los agentes de procesamiento adoptarán medidas de seguridad, técnicas y administrativas que puedan proteger los datos personales de accesos no autorizados y situaciones accidentales o ilegales de destrucción, pérdida, alteración, comunicación o cualquier tipo de procesamiento incorrecto o ilegal. | Protección de la información <br> Gobernanza de la información <br> Detección y respuesta|
|  | Artículo 48 | El responsable debe comunicar a la autoridad nacional y al interesado todo incidente de seguridad que pueda dar lugar a riesgos o daños relevantes a los interesados. | Detección y respuesta |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Implementar medidas técnicas de seguridad para protegerse contra el acceso no autorizado a información de salud protegida electrónicamente que se transmite a través de una red de comunicaciones electrónicas. | Protección de la información |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementar un mecanismo para cifrar información de salud protegida electrónicamente cuando se considere necesario. | Protección de la información |
|  | 45 CFR 164.312(c)(2) | Implementar mecanismos electrónicos para corroborar que la información de salud protegida electrónicamente no se ha modificado o destruido de forma no autorizada. | Gobernanza de la información |
|  | 45 CFR 164.316(b)(1)(i) | Si esta subparte requiere que se documente una acción, actividad o evaluación, mantenga un registro escrito (que puede ser electrónico) de la acción, actividad o evaluación | Gobernanza de la información |
|  | 45 CFR 164.316(b)(1)(ii) | Conservar la documentación exigida por el párrafo (b)(1) de esta sección durante 6 años a partir de la fecha de creación o la fecha en que fue efectiva por última vez, la que sea posterior. | Gobernanza de la información |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementar procedimientos para revisar periódicamente los registros de actividad del sistema de información, como registros de auditoría, informes de acceso e informes de seguimiento de incidentes de seguridad | Detección y respuesta |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identificar y responder a incidentes de seguridad sospechosos o conocidos; mitigar, en la medida de lo posible, efectos negativos de los incidentes de seguridad que se conozcan en la entidad cubierta o la empresa asociada y documentar incidencias de seguridad y sus resultados. | Detección y respuesta |
|  | 45 C.F.R. 164.312(b) | Implemente mecanismos de hardware, software y procedimientos que registren y examinen la actividad en sistemas de información que contienen o usan información de salud protegida electrónicamente. | Detección y respuesta |
| CCPA | 1798.105(c) | Una empresa que reciba una solicitud verificable de un consumidor para eliminar la información personal del consumidor de acuerdo con la subdivisión (a) de esta sección eliminará la información personal del consumidor de sus registros y dirigirá a los proveedores de servicios a eliminar la información personal del consumidor de sus registros. | Detección y respuesta |
|  | 1798.105(d) | (excepciones a 1798.105(c) <br> No se requiere que una empresa o un proveedor de servicios cumplan con la solicitud de un consumidor de eliminar la información personal del consumidor si es necesario que la empresa o el proveedor de servicios mantengan la información personal del consumidor con el fin de: (consulte el reglamento actual para obtener información adicional). | Detección y respuesta |
|||||

> [!IMPORTANT]
> Esto no está pensado para ser una lista exhaustiva. Consulte al [Administrador de cumplimiento](../compliance/compliance-manager.md) o al asesor legal o de cumplimiento para obtener más información sobre la aplicabilidad de las secciones mencionadas en las categorías de control técnico enumeradas.

## <a name="knowing-your-data"></a>Conocer los datos

Independientemente de las normativas a las que está sujeto, donde los distintos tipos de datos de usuario dentro y fuera de su organización interactúan con sus sistemas son factores importantes que pueden afectar a su estrategia general de protección de datos personales, sujeto a las normativas del sector y del gobierno que se aplican a su organización. Esto incluye dónde se almacenan los datos personales, qué tipo es y cuánto hay y en qué circunstancias se recopilaron.

![Conocer los datos: qué tipo es, cuánto hay y en qué circunstancias se recopilaron.](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Portabilidad de los datos

Los datos también se mueven con el tiempo a medida que se procesan, se refina y otras versiones se derivan de ellos. Una instantánea inicial nunca es suficiente. Debe haber un proceso continuo para conocer los datos. Esto representa uno de los mayores desafíos para las organizaciones grandes que administran volúmenes significativos de datos personales. Las organizaciones que no abordan el problema de "conocer sus datos" podrían acabar con un riesgo muy alto y posibles multas de las agencias reglamentarias.

![Ciclo de vida de datos](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)

### <a name="where-the-personal-data-is"></a>Dónde están los datos personales

Para abordar las regulaciones de privacidad de datos, no puede basarse en nociones generales de dónde cree que pueden existir datos personales, ya sea ahora o en el futuro. Las normativas de privacidad de datos requieren que las organizaciones demuestren que saben dónde están los datos personales de forma continua. Esto hace que sea importante tomar una instantánea inicial de todos los orígenes de datos para el posible almacenamiento de información personal, incluido el entorno Microsoft 365, y establecer mecanismos para la supervisión y detección continuas.

Si aún no ha evaluado la preparación general y los riesgos asociados con las normativas de privacidad de datos, use el siguiente marco de 3 pasos para empezar.

![Pasos para evaluar la preparación general y los riesgos asociados con las normativas de privacidad de datos](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

> [!NOTE]
> Este artículo y su contenido no están destinados a tomar el lugar de los servicios de asesoramiento jurídico. Solo proporciona algunas instrucciones básicas y vínculos a herramientas que pueden ser de ayuda en las primeras etapas de la evaluación.

## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Paso 1: Desarrollar una comprensión básica de los escenarios de datos personales de su organización

Debe medir la exposición a los riesgos de privacidad de datos en función del tipo de datos personales que administra actualmente, dónde se almacenan, qué controles de protección se colocan en él, cómo se administra su ciclo de vida y quién tiene acceso a ellos.

Como punto de partida, es importante realizar un inventario de los tipos de datos personales que existen en el entorno Microsoft 365 usuario. Use estas categorías:

- Datos de empleados necesarios para llevar a cabo funciones empresariales diarias
- Datos que la organización tiene sobre sus clientes empresariales, partners y otras relaciones en el escenario de negocio a empresa (B2B)
- Datos que la organización tiene sobre consumidores que proporcionan información a los servicios en línea que administra la organización en el escenario de negocio a cliente (B2C)

Este es un ejemplo de los diferentes tipos de datos para los departamentos típicos de una organización.

![Tipos de datos personales](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

La mayoría de los datos personales que están sujetos a la regulación de privacidad de datos normalmente se recopilan y almacenan fuera de Microsoft 365. Los datos personales de aplicaciones móviles o web orientadas al consumidor tendrían que haber sido exportados de dichas aplicaciones a Microsoft 365 para estar sujetos al examen de privacidad de datos dentro de Microsoft 365.

La exposición a la privacidad de datos en Microsoft 365 puede ser más limitada en relación con las aplicaciones web y los sistemas CRM, que esta solución no aborda.

También es importante tener en cuenta los siguientes desafíos comunes de cumplimiento de privacidad de datos al evaluar su perfil de riesgo:

 - **Distribución de datos personales.** ¿Qué tan dispersa es la información sobre un asunto determinado? ¿Es lo suficientemente conocido como para convencer a los organismos reguladores de que hay controles adecuados? ¿Se puede investigar y corregir si es necesario?
- **Proteger contra la exfiltración.** ¿Cómo se protegen los datos personales de un determinado tipo o origen para que no se comprometan y cómo responder si lo fue?
- **Protección frente al riesgo.** ¿Qué mecanismos de protección de la información son adecuados en relación con el riesgo y cómo mantener la continuidad y productividad del negocio y minimizar el impacto del usuario final si es necesaria la intervención del usuario final? Por ejemplo, ¿se debe usar la clasificación manual o el cifrado?
- **Retención de datos personales.** ¿Durante cuánto tiempo es necesario mantener la información que contiene datos personales por motivos empresariales válidos y cómo evitar prácticas de mantenimiento para siempre pasadas, equilibradas con las necesidades de retención para la continuidad empresarial?
- **Controlar solicitudes de interesados.** ¿Qué mecanismos se necesitan para controlar las solicitudes de interesados (DSR) y las acciones correctivas, como anonimización, redacción y eliminación?
- **Supervisión e informes continuos.** ¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los diferentes tipos de datos y orígenes?
- **Limitaciones en el procesamiento de datos.** ¿Existen limitaciones en el uso de datos para la información recopilada o almacenada a través de estos métodos que la organización debe reflejar en los controles de privacidad? Por ejemplo, los compromisos de que el personal de ventas no usará datos personales pueden requerir que su organización ponga en marcha mecanismos para impedir la transferencia o el almacenamiento de esa información en sistemas asociados con la organización de ventas.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Datos de empleados necesarios para llevar a cabo funciones empresariales diarias

Por naturaleza, las organizaciones necesitan recopilar datos sobre los empleados con fines de identidad electrónica y recursos humanos, sujeto a lo que acepten en sus contratos de empleados. Siempre que una persona trabaje para una empresa, esto no suele ser un problema. Es posible que la organización quiera poner en marcha mecanismos para evitar que los actores malintencionados exfiltre o filtre datos personales de los empleados.

Si una persona deja una empresa, las organizaciones suelen tener procesos, procedimientos y programaciones de retención y eliminación para quitar cuentas de usuario, retirar buzones y unidades personales y cambiar el estado de los empleados en aspectos como los sistemas de recursos humanos. En situaciones en las que hay litigios, un empleado u otra parte de una investigación legal puede tener motivos válidos para obtener información sobre los datos personales almacenados en los sistemas de la organización. En algunas ocasiones, esa parte puede solicitar que dichos datos se quiten o anonimizar.

Para satisfacer estas necesidades, las organizaciones deben tener procesos y procedimientos que acojan las necesidades de prevención, investigación y corrección para facilitar dichas solicitudes, y señalar que cierta información sobre un empleado puede considerarse razonablemente crucial para la continuidad empresarial. Por ejemplo, información de que un individuo hizo un archivo o realizó una función.

> [!NOTE]
> Para obtener técnicas de investigación y corrección para datos personales en Microsoft 365, vea el [artículo supervisar y responder](information-protection-deploy-monitor-respond.md). También puede usar esquemas automatizados de clasificación y protección para asegurarse de que los datos personales se controlan mientras están dentro de la organización, así como evitar que abandone la organización en situaciones de actor malintencionado. Vea el [artículo de información de protección](information-protection-deploy-protect-information.md) para obtener más información.

### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Datos que la organización tiene sobre sus clientes empresariales en el escenario B2B

La recopilación de información B2B también es un desafío porque es posible que su organización necesite mantener registros de nombres de clientes y transacciones en sus distintos sistemas con fines de continuidad empresarial, pero protege esa información de filtraciones involuntarias o malintencionadas. Al igual que los datos de los empleados, las organizaciones deben tener directivas, procedimientos y controles técnicos para proteger dichos datos, así como eliminarlos según las programaciones de retención y eliminación definidas.

Normalmente, los contratos con clientes externos, partners y las otras entidades con las que la organización hace negocios tendrán un lenguaje que aborda el tratamiento de dichos datos, incluida la protección, retención y eliminación tanto durante como después de que la entidad tenga una relación con la organización.

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Datos que la organización tiene sobre consumidores que proporcionan información a los servicios en línea que administra la organización en el escenario B2C

Esta categoría es la que más personas piensa en la privacidad de datos, debido a muchas instancias públicas de pérdida de datos de clientes. Esto puede ser intencionado, como un tercero bajo contrato con el proveedor, o involuntario, como la exfiltración por parte de un actor malintencionado. La protección de datos de los consumidores es una de las principales razones por las que la UE y otros países han promulgó estas normativas. Las normativas de privacidad de datos como RGPD y CCPA requieren que realice la planeación de:

- [Planes de acción](/compliance/regulatory/gdpr-action-plan) [y listas de comprobación de preparación para la responsabilidad](/compliance/regulatory/gdpr-arc-Office365)
- [Evaluaciones de impacto de protección de datos](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Notificaciones de infracciones](/compliance/regulatory/gdpr-breach-Office365)
- [Solicitudes de interesados](/compliance/regulatory/gdpr-dsr-Office365)

Si su organización no realiza una gran cantidad de recopilación de datos directamente desde el consumidor, esta categoría puede ser menos un problema. Sin embargo, es posible que deba seguir los procesos descritos en estos artículos para lograr el cumplimiento.

### <a name="step-1-summary"></a>Resumen del paso 1

Comprender su exposición a los riesgos y a la regulación de privacidad de datos es un primer paso importante que se basa en una comprensión básica de los escenarios de datos personales de su organización.

Si no tiene datos personales de consumidores en su entorno de Microsoft 365 o se limita a determinadas partes del entorno y la necesidad de un control técnico se basa en que existe una exposición de datos de tipo consumidor, es posible que ese control técnico solo necesite emplearse en partes de alto riesgo del entorno, no en todas partes.

Aunque una recomendación de conjunto de controles estándar o de organización externa, como por ejemplo desde el Administrador de cumplimiento en Microsoft 365, puede ayudar a informar a su estrategia de control, la elección de la implementación debe estar controlada por el reconocimiento del inventario de datos para cuantificar su exposición real a riesgos.

La mayoría de las organizaciones estarán expuestas a uno de los escenarios anteriores. Es importante adoptar un enfoque holístico para la evaluación.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Paso 2: Evaluar su preparación para cumplir con las normativas de privacidad de datos

Aunque son específicas del RGPD, las preguntas que se plantean en la herramienta gratuita de evaluación del RGPD de [Microsoft](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) proporcionan un buen comienzo para comprender la preparación general de la privacidad de los datos.

Las organizaciones sujetas a otras normativas de privacidad de datos, como CCPA en los Estados Unidos o LGPD de Brasil, también pueden beneficiarse del inventario de preparación de esta herramienta debido a las disposiciones superpuestas con el RGPD.

La evaluación del RGPD consta de estas secciones:

| Sección | Descripción |
|:-------|:-----|
| Gobierno | <ol><li>¿La directiva de privacidad establece explícitamente qué información de datos se está procesando? </li><li>¿Ejecuta periódicamente evaluaciones de impacto en la privacidad (CA)? </li><li> ¿Usa una herramienta para administrar la información personal (PI)? </li><li> ¿Tiene autoridad legal para llevar a cabo negocios con datos de PI en una determinada persona? ¿Realiza un seguimiento del consentimiento de los datos? </li><li> ¿Realiza un seguimiento, implementa y administra controles de auditoría? ¿Supervisa las pérdidas de datos? </li></ol>|
| Eliminación y notificación | <ol><li>¿Da instrucciones explícitas sobre cómo se puede acceder a los datos de los usuarios? </li><li> ¿Tiene procesos documentados para controlar el consentimiento de no participar? </li><li> ¿Tiene un proceso de eliminación automatizada para los datos? </li><li>   ¿Tiene un proceso para validar la identidad al interactuar con un cliente? </li></ol>|
| Mitigación de riesgos y seguridad de la información | <ol><li>¿Usa herramientas para examinar datos no estructurados? </li><li>¿Están todos los servidores actualizados y aprovecha los firewalls para protegerlos? </li><li>¿Ejecuta copias de seguridad regulares de los servidores? </li><li>¿Supervisa activamente las pérdidas de datos? </li><li>¿Cifra los datos en reposo y en transmisión? </li></ol>|
| Administración de directivas | <ol><li>¿Cómo administra las reglas corporativas de enlace (BCR)? </li><li>¿Realiza un seguimiento del consentimiento de los datos? </li><li> En una escala de 1 a 5, con 5 cubiertos por completo, ¿los contratos cubren las clasificaciones de datos y los requisitos de tratamiento? </li><li>¿Tiene y prueba periódicamente un plan de respuesta a incidentes? </li><li>¿Qué directiva usa para administrar el acceso? </li></ol>|
|||

## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Paso 3: Identificar los tipos de información confidencial que se producen en el Microsoft 365 de datos.

Este paso implica la identificación de tipos de información confidencial específicos que están sujetos a controles normativos específicos, así como la aparición de ellos en el entorno Microsoft 365 específico.

Encontrar contenido en el entorno que contenga personal puede ser una tarea formidable, que anteriormente implicaba una combinación de usar búsqueda de cumplimiento, exhibición de documentos electrónicos, Advanced eDiscovery, DLP y auditoría.

Con la  nueva solución de clasificación de datos en el [](../compliance/data-classification-content-explorer.md) Centro de administración de Cumplimiento de Microsoft, esto se ha vuelto mucho más fácil con la funcionalidad explorador de contenido, que funciona con tipos de información confidencial integrados o personalizados, incluidos los relacionados con datos personales.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

El Centro de administración de cumplimiento de Microsoft viene cargado previamente con más de 100 tipos de información confidencial, la mayoría de ellos relacionados con la identificación y localización de datos personales. Estos tipos de información confidencial integrados pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuenta bancaria, números de pasaporte y mucho más, en función de patrones definidos por una expresión regular (regex) o una función. Para obtener más información, consulte [Qué buscan los tipos de información confidencial](../compliance/sensitive-information-type-entity-definitions.md).

Si necesita identificar y proteger un tipo de elementos confidenciales específicos o regionales de la organización, como un formato personalizado para los id. de los empleados u otra información personal que aún no está cubierta por un tipo de información confidencial integrado, puede crear un tipo de información confidencial personalizado con estos métodos:

- PowerShell
- Reglas personalizadas con coincidencia exacta de datos (EDM)
- A través de la interfaz de usuario de administración del Centro de cumplimiento, como se resalta en el artículo [Use Compliance Score and Compliance Manager](information-protection-deploy-compliance.md)

También puede personalizar un tipo de información confidencial integrada existente.

Vea estos artículos para obtener más información:

- [Personalizar un tipo de información confidencial integrado](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Obtener más información acerca de los tipos de información confidencial](../compliance/sensitive-information-type-learn-about.md)
- [Crear un tipo de información confidencial personalizado en el Centro de seguridad y cumplimiento](../compliance/create-a-custom-sensitive-information-type.md)
- [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Explorador de contenido

Una herramienta importante que para determinar la aparición de [](../compliance/data-classification-content-explorer.md) elementos confidenciales en su entorno es el nuevo Explorador de contenido en el centro de administración Microsoft 365 cumplimiento. Se trata de una herramienta automatizada para el examen inicial y continuo de toda la suscripción Microsoft 365 para la aparición de tipos de información confidencial y la presentación de los resultados.

La nueva herramienta explorador de contenido le permite identificar rápidamente las ubicaciones de elementos confidenciales en su entorno, con tipos de información confidencial integrados o personalizados. Esto puede implicar el establecimiento de un proceso y la responsabilidad asignada de investigar periódicamente la presencia y ubicación de elementos confidenciales.

Junto con los otros pasos resaltados en este artículo, esto proporciona un punto de partida para identificar la exposición general al riesgo, la preparación y la ubicación de los elementos confidenciales para proteger mediante la configuración y supervisión Microsoft 365 planeada.

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Otros métodos para identificar datos personales en su entorno

Además del Explorador de contenido, las organizaciones tienen acceso a la funcionalidad búsqueda de contenido para producir búsquedas personalizadas para buscar datos personales en su entorno, mediante criterios de búsqueda avanzados y filtros personalizados.

En este artículo se proporcionan instrucciones detalladas sobre el uso de la búsqueda de contenido para la detección de [datos personales.](/compliance/regulatory/gdpr) La búsqueda de contenido y otras técnicas de detección también se exploran en [los DSR para el RGPD y el CCPA.](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs)

En el artículo supervisar y responder se proporcionan información adicional sobre las técnicas de investigación y corrección de datos personales Microsoft 365 en el [artículo de supervisión y respuesta](information-protection-deploy-monitor-respond.md).

> [!NOTE]
> Para encontrar la información confidencial que tiene en los archivos almacenados localmente, consulte [Azure Information Protection](/azure/information-protection/quickstart-findsensitiveinfo).