---
title: Evaluación de riesgos de privacidad de datos e identificación de elementos confidenciales con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: Determine las regulaciones de privacidad de datos, los escenarios pertinentes, su preparación y los tipos de información confidencial que se encuentran en su entorno de Microsoft 365.
ms.openlocfilehash: 2615244f76fc17181fa2aa2d04a11c99f05474a1
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985704"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Evaluación de riesgos de privacidad de datos e identificación de elementos confidenciales con Microsoft 365

Evaluar las regulaciones de privacidad de datos y los riesgos a los que está sujeta su organización es un primer paso antes de implementar las acciones de mejora relacionadas, incluidas las acciones que se pueden lograr con las características y servicios de Microsoft 365.

## <a name="potentially-applicable-data-privacy-regulations"></a>Normativas de privacidad de datos potencialmente aplicables

Para obtener una buena referencia sobre el marco normativo más amplio para las regulaciones de privacidad de datos, consulte el [Portal de confianza de servicios de Microsoft](https://servicetrust.microsoft.com/) y la [serie de artículos sobre el reglamento general de protección de datos (RGPD).](/compliance/regulatory/gdpr) Revise también los materiales sobre las regulaciones a las que puede estar sujeto en su sector o región.

### <a name="gdpr"></a>RGPD

El RGPD es el más conocido y citado de las regulaciones de privacidad de datos. Regula la recopilación, el almacenamiento, el procesamiento y el uso compartido de cualquier dato personal relacionado con una persona física identificada o identificable residente en la Unión Europea (UE).

De acuerdo con el artículo 4 del RGPD:

- «datos personales»: toda información relativa a una persona física identificada o identificable («interesado»); una persona física identificable es aquella que puede identificarse, directa o indirectamente, en particular por referencia a un identificador como un nombre, un número de identificación, datos de ubicación, un identificador en línea o a uno o varios factores específicos de la identidad física, fisiológica, genética, mental, económica, cultural o social de esa persona física.

### <a name="iso-27001"></a>ISO 27001

La adhesión a otras normas como la ISO 27001 también ha sido reconocida por varias autoridades de supervisión europeas como un proxy válido de intención en todo el espectro de personas, procesos y tecnología. Los estándares que especifica la superposición y el cumplimiento de los mecanismos de protección basados en ISO-27001 pueden considerarse un proxy que cumple algunas obligaciones de privacidad en determinadas circunstancias.

### <a name="other-data-privacy-regulations"></a>Otras regulaciones de privacidad de datos

Otras normativas de privacidad de datos destacadas también especifican requisitos para el tratamiento de datos personales.

En el Estados Unidos, estos incluyen la Ley de Protección al Consumidor de California ([CCPA](/compliance/regulatory/ccpa-faq)), HIPAA-HITECH (Estados Unidos ley de privacidad de atención médica) y la Ley Graham Leach Bliley (GLBA). Otras regulaciones específicas del estado también están en vigor o en desarrollo.

En todo el mundo, más ejemplos incluyen la Ley Nacional de Implementación del RGPD (BDSG) de Alemania, la Ley de protección de datos de Brasil (LGPD) y muchos otros.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Asignación de normativas a categorías de control técnico de Microsoft 365

Muchas de las regulaciones relacionadas con la privacidad de datos tienen requisitos superpuestos, por lo que debe comprender a qué normativas están sujetas antes de desarrollar cualquier esquema de control técnico.

Para una referencia posterior en los artículos de esta solución general, en esta tabla se proporcionan extractos de un muestreo de las regulaciones de privacidad de datos.

|Regulación|Artículo/sección|Extracto|Categorías de control técnico aplicables|
|---|---|---|---|
|RGPD|Artículo 5, apartado 1, letra f)|Los datos personales se procesarán de forma que garantice la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida accidental, la destrucción o el daño, utilizando las medidas técnicas u organizativas adecuadas («integridad y confidencialidad».|(Todos) <br> Identidad <br> Device <br> Protección contra amenazas <br> Protección de la información <br> Gobernanza de la información <br> Detección y respuesta|
||Artículo 32)(1)(a)|Teniendo en cuenta el estado de la técnica, los costos de ejecución y la naturaleza, el ámbito, el contexto y los fines del tratamiento, así como el riesgo de variación de probabilidad y gravedad para los derechos y libertades de las personas físicas, el responsable y el encargado de la tratamiento aplicarán las medidas técnicas y organizativas adecuadas para garantizar un nivel de seguridad adecuado al riesgo,  incluyendo, entre otras cosas, según corresponda: (a) la seudónimo y el cifrado de datos personales.|Protección de la información|
||Artículo 13)(2)(a)|"... En el momento en que se obtengan los datos personales, el responsable del tratamiento proporcionará al interesado la siguiente información adicional necesaria para garantizar un tratamiento justo y transparente: (a) el período durante el cual se almacenarán los datos personales, o si no es posible, los criterios utilizados para determinar ese período.|Gobernanza de la información|
||Artículo 15)(1)(e)|El interesado tendrá derecho a obtener de la confirmación del responsable de la tratamiento si se están procesando o no los datos personales que le conciernen, y en su caso, el acceso a los datos personales y la siguiente información: (e) la existencia del derecho a solicitar al responsable la rectificación o eliminación de datos personales o la restricción del tratamiento de datos personales relativos al interesado o a oponerse a dichos datos Tratamiento|Detección y respuesta|
|LGPD|Artículo 46|Los agentes encargados del tratamiento adoptarán medidas de seguridad, técnicas y administrativas que puedan proteger los datos personales frente a accesos no autorizados y situaciones accidentales o ilegales de destrucción, pérdida, alteración, comunicación o cualquier tipo de tratamiento inadecuado o ilegal.|Protección de la información <br> Gobernanza de la información <br> Detección y respuesta|
||Artículo 48|El responsable debe comunicar a la autoridad nacional y al interesado todo incidente de seguridad que pueda dar lugar a riesgos o daños relevantes a los interesados.|Detección y respuesta|
|HIPPA-HITECH|45 CFR 164.312(e)(1)|Implementar medidas técnicas de seguridad para protegerse contra el acceso no autorizado a información de salud protegida electrónicamente que se transmite a través de una red de comunicaciones electrónicas.|Protección de la información|
||45 C.F.R. 164.312(e)(2)(ii)|Implementar un mecanismo para cifrar información de salud protegida electrónicamente cuando se considere necesario.|Protección de la información|
||45 CFR 164.312(c)(2)|Implemente mecanismos electrónicos para corroborar que la información sanitaria protegida electrónica no se ha modificado ni destruido de forma no autorizada.|Gobernanza de la información|
||45 CFR 164.316(b)(1)(i)|Si esta subparte requiere que se documente una acción, actividad o evaluación, mantenga un registro escrito (que puede ser electrónico) de la acción, actividad o evaluación.|Gobernanza de la información|
||45 CFR 164.316(b)(1)(ii)|Conservar la documentación exigida por el párrafo (b)(1) de esta sección durante 6 años a partir de la fecha de creación o la fecha en que fue efectiva por última vez, la que sea posterior.|Gobernanza de la información|
||45 C.F.R. 164.308(a)(1)(ii)(D)|Implementar procedimientos para revisar periódicamente los registros de actividad del sistema de información, como registros de auditoría, informes de acceso e informes de seguimiento de incidentes de seguridad|Detección y respuesta|
||45 C.F.R. 164.308(a)(6)(ii)|Identificar y responder a incidentes de seguridad sospechosos o conocidos; mitigar, en la medida de lo posible, efectos negativos de los incidentes de seguridad que se conozcan en la entidad cubierta o la empresa asociada y documentar incidencias de seguridad y sus resultados.|Detección y respuesta|
||45 C.F.R. 164.312(b)|Implemente mecanismos de hardware, software y procedimientos que registren y examinen la actividad en sistemas de información que contienen o usan información de salud protegida electrónicamente.|Detección y respuesta|
|CCPA|1798.105(c)|Una empresa que reciba una solicitud verificable de un consumidor para eliminar la información personal del consumidor de conformidad con la subdivisión (a) de esta sección eliminará la información personal del consumidor de sus registros y dirigirá a los proveedores de servicios que eliminen la información personal del consumidor de sus registros.|Detección y respuesta|
||1798.105(d)|(excepciones a 1798.105(c) <br> Una empresa o un proveedor de servicios no deberán cumplir con la solicitud de un consumidor de eliminar la información personal del consumidor si es necesario que la empresa o el proveedor de servicios mantengan la información personal del consumidor con el fin de: (consulte el reglamento actual para obtener información adicional).|Detección y respuesta|
|||||

> [!IMPORTANT]
> Esto no está pensado para ser una lista exhaustiva. Consulte [el Administrador de cumplimiento](../compliance/compliance-manager.md) o su asesor legal o de cumplimiento para obtener más información sobre la aplicabilidad de las secciones citadas en las categorías de control técnico enumeradas.

## <a name="knowing-your-data"></a>Conocer los datos

Independientemente de las regulaciones a las que esté sujeto, donde diferentes tipos de datos de usuario dentro y fuera de su organización interactúan con sus sistemas son factores importantes que pueden afectar a su estrategia de protección de datos personales general, sujeto a las regulaciones del sector y del gobierno que se aplican a su organización. Esto incluye dónde se almacenan los datos personales, qué tipo es y cuánto de ellos hay y en qué circunstancias se recopilaron.

![Conocer los datos: qué tipo es y cuánto hay y en qué circunstancias se recopilaron.](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Portabilidad de los datos

Los datos también se mueven con el tiempo a medida que se procesan, refinan y otras versiones se derivan de ellos. Una instantánea inicial nunca es suficiente. Debe haber un proceso continuo para conocer los datos. Esto representa uno de los mayores desafíos para las grandes organizaciones que controlan volúmenes significativos de datos personales. Las organizaciones que no abordan el problema de "conocer sus datos" podrían acabar con un riesgo muy alto y posibles multas de las agencias reguladoras.

![Ciclo de vida de los datos.](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)

### <a name="where-the-personal-data-is"></a>Dónde están los datos personales

Para abordar las regulaciones de privacidad de datos, no puede basarse en nociones generales de dónde cree que pueden existir datos personales, ya sea ahora o en el futuro. Las regulaciones de privacidad de datos requieren que las organizaciones demuestren que saben dónde están los datos personales de forma continuada. Esto hace que sea importante tomar una instantánea inicial de todos los orígenes de datos para el posible almacenamiento de información personal, incluido el entorno de Microsoft 365, y establecer mecanismos para la supervisión y detección continuas.

Si aún no ha evaluado la preparación general y el riesgo asociados a las regulaciones de privacidad de datos, use el siguiente marco de 3 pasos para empezar.

![Pasos para evaluar la preparación general y el riesgo asociados a las regulaciones de privacidad de datos.](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

> [!NOTE]
> Este artículo y su contenido no están destinados a ocupar el lugar de los servicios de asesoramiento legal. Solo proporciona algunas instrucciones básicas y vínculos a herramientas que pueden ser de ayuda en las primeras fases de su evaluación.

## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Paso 1: Desarrollar una comprensión fundamental de los escenarios de datos personales de su organización

Debe medir la exposición al riesgo de privacidad de los datos en función del tipo de datos personales que administra actualmente, dónde se almacenan, qué controles de protección se colocan en él, cómo se administra su ciclo de vida y quién tiene acceso a ellos.

Como punto de partida, es importante hacer un inventario de los tipos de datos personales que existen en su entorno de Microsoft 365. Use estas categorías:

- Datos de empleados necesarios para llevar a cabo funciones empresariales diarias
- Datos que la organización tiene sobre sus clientes empresariales, asociados y otras relaciones en el escenario de negocio a negocio (B2B)
- Datos que la organización tiene sobre los consumidores que proporcionan información para servicios en línea que la organización administra en el escenario de negocio a cliente (B2C)

Este es un ejemplo de los diferentes tipos de datos para los departamentos típicos de una organización.

![Tipos de datos personales.](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Gran parte de los datos personales que están sujetos a la normativa de privacidad de datos se recopilan y almacenan normalmente fuera de Microsoft 365. Cualquier dato personal de aplicaciones web o móviles orientadas al consumidor tendría que haberse exportado desde dichas aplicaciones a Microsoft 365 para estar sujeto al examen de privacidad de los datos en Microsoft 365.

La exposición a la privacidad de los datos en Microsoft 365 puede estar más limitada en relación con las aplicaciones web y los sistemas CRM, que esta solución no aborda.

También es importante pensar en los siguientes desafíos comunes de cumplimiento de privacidad de datos al evaluar el perfil de riesgo:

- **Distribución de datos personales.** ¿Qué dispersión tiene la información sobre un sujeto determinado? ¿Se sabe lo suficiente como para convencer a los organismos reguladores de que existen controles adecuados? ¿Se puede investigar y corregir si es necesario?
- **Protección contra la filtración.** ¿Cómo se protegen los datos personales de un tipo o origen determinados de que se ponen en peligro y cómo responder si lo están?
- **Protección frente a riesgo.** ¿Qué mecanismos de protección de la información son adecuados en relación con el riesgo y cómo mantener la continuidad empresarial y la productividad, y minimizar el impacto del usuario final si se requiere la intervención del usuario final? Por ejemplo, ¿se debe usar la clasificación manual o el cifrado?
- **Retención de datos personales.** ¿Cuánto tiempo necesita mantenerse la información que contiene datos personales por motivos empresariales válidos y cómo evitar prácticas anteriores de mantenimiento para siempre, equilibradas con las necesidades de retención para la continuidad empresarial?
- **Control de solicitudes del interesado.** ¿Qué mecanismos serán necesarios para controlar las solicitudes del interesado (DSR) y las acciones correctivas, como anonimización, censura y eliminación?
- **Supervisión e informes continuos.** ¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los distintos tipos de datos y orígenes?
- **Limitaciones en el procesamiento de datos.** ¿Existen limitaciones en el uso de datos para la información recopilada o almacenada a través de estos métodos que la organización debe reflejar en los controles de privacidad? Por ejemplo, los compromisos de que el personal de ventas no usará los datos personales pueden requerir que su organización ponga en marcha mecanismos para evitar la transferencia o el almacenamiento de esa información en sistemas asociados a la organización de ventas.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Datos de empleados necesarios para llevar a cabo funciones empresariales diarias

Por naturaleza, las organizaciones deben recopilar datos sobre los empleados con fines de identidad electrónica y RR. HH., sujetos a lo que acepten en sus contratos de empleados. Siempre que una persona trabaje para una empresa, esto no suele ser un problema. Es posible que la organización quiera establecer mecanismos para evitar que actores malintencionados exfiltre o filtre datos personales de los empleados.

Si una persona deja una empresa, las organizaciones suelen tener procesos, procedimientos y programaciones de retención y eliminación para quitar cuentas de usuario, retirar buzones y unidades personales, y cambiar el estado de los empleados en aspectos como los sistemas de recursos humanos. En situaciones en las que se produce un litigio, un empleado u otra parte en una investigación legal puede tener razones válidas para obtener información sobre los datos personales almacenados en los sistemas de la organización. En algunas ocasiones, esa parte puede solicitar que dichos datos se quiten o anonimicen.

Para abordar estas necesidades, las organizaciones deben tener procesos y procedimientos que aborden las necesidades preventivas, de detectives y correctivas para facilitar dichas solicitudes, teniendo en cuenta que cierta información sobre un empleado puede considerarse razonablemente crucial para la continuidad empresarial. Por ejemplo, información de que una persona creó un archivo o realizó una función.

> [!NOTE]
> Para conocer las técnicas de investigación y corrección de datos personales en Microsoft 365, consulte el [artículo supervisión y respuesta](information-protection-deploy-monitor-respond.md). También puede emplear esquemas de clasificación y protección automatizados para asegurarse de que los datos personales se controlan dentro de la organización, así como para evitar que salgan de la organización en situaciones de actores malintencionados. Consulte el [artículo sobre la información de protección](information-protection-deploy-protect-information.md) para obtener más información.

### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Datos que la organización tiene sobre sus clientes empresariales en el escenario B2B

La recopilación de información B2B también es un desafío porque es posible que su organización necesite mantener registros de nombres de clientes y transacciones en sus diversos sistemas con fines de continuidad empresarial y, sin embargo, proteger esa información de la filtración involuntaria o malintencionada. Al igual que los datos de los empleados, las organizaciones deben tener directivas, procedimientos y controles técnicos para proteger dichos datos, así como eliminarlos según las programaciones de retención y eliminación definidas.

Normalmente, los contratos con clientes externos, asociados y otras entidades con las que la organización realiza negocios tendrán un lenguaje que aborde el control de dichos datos, incluida la protección, la retención y la eliminación, tanto durante como después de que la entidad tenga una relación con la organización.

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Datos que la organización tiene sobre los consumidores que proporcionan información para servicios en línea que la organización administra en el escenario B2C

Esta categoría es la que más gente piensa en la privacidad de los datos, debido a muchas instancias públicas de pérdida de datos de los clientes. Esto puede ser intencionado, como un tercero bajo contrato con el proveedor, o involuntaria, como la filtración por parte de un actor malintencionado. La protección de datos de los consumidores es una de las razones principales por las que la UE y otros han promulgado estas normas. Las regulaciones de privacidad de datos como RGPD y CCPA requieren que realice la planeación de:

- [Planes de acción](/compliance/regulatory/gdpr-action-plan) y [listas de comprobación de preparación para la rendición de cuentas](/compliance/regulatory/gdpr-arc-Office365)
- [Evaluaciones de impacto de protección de datos](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Notificaciones de infracción](/compliance/regulatory/gdpr-breach-Office365)
- [Solicitudes de interesados](/compliance/regulatory/gdpr-dsr-Office365)

Si su organización no realiza una gran cantidad de recopilación de datos directa desde el consumidor, esta categoría puede ser menos un problema. Sin embargo, es posible que tenga que seguir los procesos descritos en estos artículos para lograr el cumplimiento.

### <a name="step-1-summary"></a>Resumen del paso 1

Comprender su exposición a la regulación de privacidad de datos y riesgos es un primer paso importante que se basa en una comprensión fundamental de los escenarios de datos personales de su organización.

Si no tiene datos personales de consumidores en su entorno de Microsoft 365 o se limita a ciertas partes del entorno y la necesidad de un control técnico se basa en la exposición de datos de tipo consumidor, es posible que ese control técnico solo tenga que emplearse en partes de alto riesgo del entorno, no en todas partes.

Aunque una organización externa o una recomendación de conjunto de control estándar, como desde el Administrador de cumplimiento de Microsoft 365, puede ayudar a informar a su estrategia de control, su elección de implementación debe basarse en el reconocimiento del inventario de datos para cuantificar la exposición real al riesgo.

La mayoría de las organizaciones tendrán cierta exposición a uno de los escenarios anteriores. Es importante adoptar un enfoque holístico para la evaluación.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Paso 2: Evaluar su preparación para cumplir con las regulaciones de privacidad de datos

Aunque son específicas del RGPD, las preguntas planteadas en la herramienta gratuita de [evaluación del RGPD de Microsoft](https://clouddamcdnprodep.azureedge.net/gdc/1863571/original) proporcionan un buen comienzo para comprender la preparación general de la privacidad de los datos.

Las organizaciones sujetas a otras regulaciones de privacidad de datos, como CCPA en el Estados Unidos o LGPD de Brasil, también pueden beneficiarse del inventario de preparación de esta herramienta debido a disposiciones superpuestas con el RGPD.

La evaluación del RGPD consta de estas secciones:

|Sección|Descripción|
|:-------|:-----|
|Gobernanza|<ol><li>¿Su directiva de privacidad indica explícitamente qué información de datos se está procesando? </li><li>¿Ejecuta regularmente evaluaciones de impacto de privacidad (PIA)? </li><li> ¿Usa una herramienta para administrar información personal (PI)? </li><li> ¿Tiene autoridad legal para realizar negocios con datos de PI en una persona determinada? ¿Realiza un seguimiento del consentimiento de los datos? </li><li> ¿Realiza el seguimiento, la implementación y la administración de controles de auditoría? ¿Supervisa las fugas de datos? </li></ol>|
|Eliminación y notificación|<ol><li>¿Se proporcionan instrucciones explícitas sobre cómo se puede acceder a los datos de los usuarios? </li><li> ¿Tiene procesos documentados para controlar el consentimiento de exclusión? </li><li> ¿Tiene un proceso de eliminación automatizada de datos? </li><li> ¿Tiene un proceso para validar la identidad al interactuar con un cliente? </li></ol>|
|Mitigación de riesgos y seguridad de la información|<ol><li>¿Usa herramientas para examinar datos no estructurados? </li><li>¿Están todos los servidores actualizados y aprovecha los firewalls para protegerlos? </li><li>¿Ejecuta copias de seguridad periódicas de los servidores? </li><li>¿Supervisa activamente las fugas de datos? </li><li>¿Cifra los datos en reposo y en transmisión? </li></ol>|
|Administración de directivas|<ol><li>¿Cómo se administran las reglas corporativas de enlace (BCR)? </li><li>¿Realiza un seguimiento del consentimiento de los datos? </li><li> En una escala de 1 a 5, siendo 5 completamente cubierta, ¿cubren sus contratos las clasificaciones de datos y los requisitos de control? </li><li>¿Tiene y prueba periódicamente un plan de respuesta a incidentes? </li><li>¿Qué directiva usa para administrar el acceso? </li></ol>|
|||

## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Paso 3: Identificar los tipos de información confidencial que se producen en el entorno de Microsoft 365

Este paso implica la identificación de determinados tipos de información confidencial que están sujetos a controles normativos específicos, así como la aparición de ellos en el entorno de Microsoft 365.

Buscar contenido en el entorno que contiene personal puede ser una tarea formidable, que anteriormente implicaba una combinación de búsqueda de cumplimiento, exhibición de documentos electrónicos, exhibición de documentos electrónicos (Premium), DLP y auditoría.

Con la nueva solución **de clasificación de datos** en el portal de cumplimiento Microsoft Purview, esto se ha vuelto mucho más fácil con la funcionalidad [Explorador de contenido](../compliance/data-classification-content-explorer.md), que funciona con tipos de información confidencial integrados o personalizados, incluidos los relacionados con los datos personales.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

El portal de cumplimiento Microsoft Purview viene precargado con más de 100 tipos de información confidencial, la mayoría relacionados con la identificación y localización de datos personales. Estos tipos de información confidencial integrados pueden ayudar a identificar y proteger los números de tarjeta de crédito, los números de cuenta bancaria, los números de pasaporte, etc., en función de los patrones definidos por una expresión regular (regex) o una función. Para obtener más información, consulte [Qué buscan los tipos de información confidencial](../compliance/sensitive-information-type-entity-definitions.md).

Si necesita identificar y proteger un tipo de elementos confidenciales específico de la organización o regional, como un formato personalizado para identificadores de empleado u otra información personal que aún no esté cubierta por un tipo de información confidencial integrado, puede crear un tipo de información confidencial personalizado con estos métodos:

- Security & Compliance PowerShell
- Reglas personalizadas con coincidencia exacta de datos (EDM)
- A través del portal de cumplimiento de Microsoft 365 Purview, como se resalta en el [artículo Usar la puntuación de cumplimiento y el Administrador de cumplimiento](information-protection-deploy-compliance.md)

También puede personalizar un tipo de información confidencial integrado existente.

Consulte estos artículos para obtener más información:

- [Personalizar un tipo de información confidencial integrado](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Obtener más información acerca de los tipos de información confidencial](../compliance/sensitive-information-type-learn-about.md)
- [Crear un tipo de información confidencial personalizado en el Centro de seguridad y cumplimiento](../compliance/create-a-custom-sensitive-information-type.md)
- [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos](/microsoft-365/compliance/sit-get-started-exact-data-match-based-sits-overview)

### <a name="content-explorer"></a>Explorador de contenido

Una herramienta importante que para determinar la aparición de elementos confidenciales en el entorno es el nuevo [Explorador de contenido](../compliance/data-classification-content-explorer.md) en el Centro de administración de Microsoft Purview. Se trata de una herramienta automatizada para el examen inicial y continuo de toda la suscripción de Microsoft 365 para la aparición de tipos de información confidencial y la visualización de los resultados.

La nueva herramienta Explorador de contenido permite identificar rápidamente las ubicaciones de los elementos confidenciales de su entorno, ya sea mediante tipos de información confidencial integrados o personalizados. Esto puede implicar el establecimiento de un proceso y la responsabilidad asignada de investigar periódicamente la presencia y ubicación de elementos confidenciales.

Junto con los otros pasos resaltados en este artículo, proporciona un punto de partida para identificar la exposición general al riesgo, la preparación y la ubicación de los elementos confidenciales que se protegerán a través de la configuración y supervisión planeadas de Microsoft 365.

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Otros métodos para identificar datos personales en su entorno

Además del Explorador de contenido, las organizaciones tienen acceso a la funcionalidad Búsqueda de contenido para generar búsquedas personalizadas para buscar datos personales en su entorno, mediante criterios de búsqueda avanzados y filtros personalizados.

En [este artículo](/compliance/regulatory/gdpr) se proporcionan instrucciones detalladas sobre el uso de Búsqueda de contenido para la detección de datos personales. Búsqueda de contenido y otras técnicas de detección también se exploran en [DSR para el RGPD y CCPA](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs).

En el [artículo supervisión y respuesta](information-protection-deploy-monitor-respond.md) se proporciona información adicional sobre las técnicas de investigación y corrección de datos personales de Microsoft 365.

> [!NOTE]
> Para encontrar la información confidencial que tiene en los archivos almacenados en el entorno local, consulte [Azure Information Protection](/azure/information-protection/quickstart-findsensitiveinfo).
