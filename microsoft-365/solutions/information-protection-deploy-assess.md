---
title: Evaluar los riesgos de privacidad de los datos e identificar elementos confidenciales con Microsoft 365
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
description: Determine las regulaciones de privacidad de datos, los escenarios relevantes, su preparación y los tipos de información confidencial que se encuentran en su entorno de Microsoft 365.
ms.openlocfilehash: c5a1662f5e82c8b8b9439439df0ee369d45e7616
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931907"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Evaluar los riesgos de privacidad de los datos e identificar elementos confidenciales con Microsoft 365

Evaluar las regulaciones y riesgos de privacidad de datos a los que está sujeta su organización es un primer paso clave antes de implementar cualquier acción de mejora relacionada, incluidas las que se pueden lograr con los servicios y características de Microsoft 365. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Normativas de privacidad de datos potencialmente aplicables

Para obtener una buena referencia sobre el marco normativo más amplio para las regulaciones de privacidad de datos, consulte el Portal de confianza de servicios de [Microsoft](https://servicetrust.microsoft.com/) y la serie de artículos sobre el Reglamento general de protección de datos [(RGPD),](../compliance/gdpr.md)así como otros materiales sobre las normativas a las que puede estar sujeto en su sector o región.

### <a name="gdpr"></a>RGPD

El RGPD, el más conocido y mencionado de las normas de privacidad de datos, regula la recopilación, el almacenamiento, el procesamiento y el uso compartido de los datos personales relacionados con una persona física identificada o identificable que sea residente de la Unión Europea (UE). 

De acuerdo con el artículo 4 del RGPD: 

- "datos personales": toda información relacionada con una persona física identificada o identificable ("interesado"); una persona física identificable es aquella que se puede identificar, directa o indirectamente, en particular por referencia a un identificador como un nombre, un número de identificación, datos de ubicación, un identificador en línea o a uno o más factores específicos de la identidad física, fisiológica, mental, económica, cultural o social de esa persona física.

### <a name="iso-27001"></a>ISO 27001

La adherencia a otros estándares como ISO 27001 también ha sido reconocida por varias autoridades supervisoras europea como un proxy válido de propósito en todo el espectro de personas, procesos y tecnología. Los estándares que especifica la superposición y el cumplimiento de los mecanismos de protección basados en ISO-27001 pueden considerarse un proxy que cumple algunas obligaciones de privacidad en determinadas circunstancias.

### <a name="other-data-privacy-regulations"></a>Otras normativas de privacidad de datos

Otras normativas de privacidad de datos destacadas también especifican requisitos para el tratamiento de datos personales.

En los Estados Unidos, se incluyen la Ley de Protección de Consumidores de California[(CCPA),](../compliance/ccpa-faq.md)HIPAA-HITECH (Ley de privacidad de atención sanitaria de Estados Unidos) y la Ley Leach Bliley (GLBA). Las normativas adicionales específicas del estado también están en su lugar o en desarrollo. 

En todo el mundo, algunos ejemplos adicionales incluyen la Ley nacional de implementación del RGPD (BDSG) de Alemania, la Ley de protección de datos de Brasil (LGPD) y muchas otras.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Asignación de normativas a categorías de control técnico de Microsoft 365

Muchas de las regulaciones relacionadas con la privacidad de datos tienen requisitos superpuestos, por lo que debe comprender qué normativas están sujetas antes de desarrollar cualquier esquema de control técnico. 

Para obtener una referencia posterior en los artículos de esta solución general, en esta tabla se proporcionan extractos de un muestreo de normativas de privacidad de datos. 

| Reglamento | Artículo o sección | Extracto | Categorías de control técnico aplicables |
|:-------|:-----|:-------|:-------|
| RGPD | Artículo 5(1)(f) | Los datos personales se procesarán de manera que garanticen la seguridad adecuada de los datos personales, incluida la protección contra el procesamiento no autorizado o ilegal y contra la pérdida, destrucción o daños accidentales, mediante las medidas técnicas u organizativas adecuadas ("integridad y confidencialidad".  |  (Todos) <br> Identidad <br> Dispositivo <br> Protección contra amenazas <br> Proteger la información <br> Información del Govern <br> Detectar y responder |
|  | Artículo (32)(1)(a) | Teniendo en cuenta el estado de la técnica, los costos de implementación y la naturaleza, el alcance, el contexto y los fines del tratamiento, así como el riesgo de distinta probabilidad y gravedad para los derechos y libertades de las personas físicas, el responsable y el encargado del tratamiento aplicarán las medidas técnicas y organizativas adecuadas para garantizar un nivel de seguridad adecuado para el riesgo. , incluidos entre sí según corresponda: (a) la seudonimización y el cifrado de datos personales. | Proteger la información |
|  | Artículo (13)(2)(a) | "... en el momento en que se obtengan los datos personales, el responsable del tratamiento proporcionará al interesado la siguiente información adicional necesaria para garantizar un procesamiento justo y transparente: (a) el período durante el cual se almacenarán los datos personales o, si no es posible, los criterios utilizados para determinar dicho período. | Información del Govern |
|  | Artículo (15)(1)(e) | El interesado tendrá derecho a obtener del responsable la confirmación sobre si se están procesando o no los datos personales relacionados con él y, en ese caso, el acceso a los datos personales y la siguiente información: (e) la existencia del derecho a solicitar al responsable la rectificación o eliminación de datos personales o la restricción del tratamiento de datos personales relativos al interesado o a oponerse a dicho tratamiento. | Detectar y responder |
| LGPD | Artículo 46 | Los agentes de procesamiento adoptarán medidas de seguridad, técnicas y administrativas que puedan proteger los datos personales de accesos no autorizados y situaciones accidentales o ilegales de destrucción, pérdida, alteración, comunicación o cualquier tipo de procesamiento incorrecto o ilegal. | Proteger la información <br> Información del Govern <br> Detectar y responder|
|  | Artículo 48 | El responsable debe comunicar a la autoridad nacional y al interesado todo incidente de seguridad que pueda dar lugar a riesgos o daños relevantes a los interesados. | Detectar y responder |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Implementar medidas técnicas de seguridad para protegerse contra el acceso no autorizado a información de salud protegida electrónicamente que se transmite a través de una red de comunicaciones electrónicas. | Proteger la información |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementar un mecanismo para cifrar información de salud protegida electrónicamente cuando se considere necesario. | Proteger la información |
|  | 45 CFR 164.312(c)(2) | Implementar mecanismos electrónicos para corroborar que la información de salud protegida electrónicamente no se ha modificado o destruido de forma no autorizada. | Información del Govern |
|  | 45 CFR 164.316(b)(1)(i) | Si esta subparte requiere que se documente una acción, actividad o evaluación, mantenga un registro escrito (que puede ser electrónico) de la acción, actividad o evaluación. | Información del Govern |
|  | 45 CFR 164.316(b)(1)(ii) | Conservar la documentación exigida por el párrafo (b)(1) de esta sección durante 6 años a partir de la fecha de creación o la fecha en que fue efectiva por última vez, la que sea posterior. | Información del Govern |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementar procedimientos para revisar periódicamente los registros de actividad del sistema de información, como registros de auditoría, informes de acceso e informes de seguimiento de incidentes de seguridad | Detectar y responder |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identificar y responder a incidentes de seguridad sospechosos o conocidos; mitigar, en la medida de lo posible, efectos negativos de los incidentes de seguridad que se conozcan en la entidad cubierta o la empresa asociada y documentar incidencias de seguridad y sus resultados. | Detectar y responder |
|  | 45 C.F.R. 164.312(b) | Implementar mecanismos de hardware, software y procedimientos que registren y examinen la actividad en sistemas de información que contienen o usan información de salud protegida electrónicamente. | Detectar y responder |
| CCPA | 1798.105(c) | Una empresa que reciba una solicitud verificable de un consumidor para eliminar la información personal del consumidor en virtud de la subdivisión (a) de esta sección, eliminará la información personal del consumidor de sus registros y dirigirá a los proveedores de servicios que eliminen la información personal del consumidor de sus registros. | Detectar y responder |
|  | 1798.105(d) | (excepciones a 1798.105(c) <br> Una empresa o un proveedor de servicios no estarán obligados a cumplir con la solicitud de un consumidor de eliminar la información personal del consumidor si es necesario que la empresa o el proveedor de servicios mantengan la información personal del consumidor para: (consulte el reglamento actual para obtener información adicional). | Detectar y responder |
|||||

>[!Important]
>Esto no está pensado para ser una lista exhaustiva. Consulte al [Administrador de cumplimiento](../compliance/compliance-manager.md) o al asesor legal o de cumplimiento para obtener más información sobre la aplicabilidad de las secciones mencionadas en las categorías de control técnico enumeradas.
>

## <a name="knowing-your-data"></a>Conocer los datos

Independientemente de las normativas a las que se somete, donde distintos tipos de datos de usuario dentro y fuera de su organización interactúan con sus sistemas son todos factores importantes que pueden afectar a su estrategia general de protección de datos personales, sujeto a las regulaciones gubernamentales y del sector que se aplican a su organización. Esto incluye dónde se almacenan los datos personales, qué tipo son, cuánto hay y en qué circunstancias se recopilaron.
 
![Conocer los datos: qué tipo es, cuánto hay y en qué circunstancias se recopilaron.](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Portabilidad de los datos 

Los datos también se mueven con el tiempo a medida que se procesan, se refina y otras versiones se derivan de ellos. Una instantánea inicial nunca es suficiente. Debe haber un proceso continuo para conocer los datos. Esto representa uno de los mayores desafíos para las grandes organizaciones que administran volúmenes significativos de datos personales. Las organizaciones que no abordan el problema de "conocer sus datos" podrían acabar potencialmente con un riesgo muy alto y posibles multas de las agencias reguladoras.

![El ciclo de vida de los datos](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Dónde están los datos personales

Para abordar las regulaciones de privacidad de datos, no puede confiar en nociones generales de dónde cree que pueden existir datos personales, ya sea ahora o en el futuro. Las normativas de privacidad de datos requieren que las organizaciones demuestren que saben dónde están los datos personales de forma continuada. Esto hace que sea importante tomar una instantánea inicial de todos los orígenes de datos para el posible almacenamiento de información personal, incluido su entorno de Microsoft 365, y establecer mecanismos para la supervisión y detección continuas.

Si aún no ha evaluado la preparación general y los riesgos asociados con las normativas de privacidad de datos, use el siguiente marco de tres pasos para empezar. 

![Pasos para evaluar la preparación general y los riesgos asociados con las normativas de privacidad de datos](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Este artículo y su contenido no están diseñados para asumir el lugar de los servicios de asesoría legal. Solo proporciona algunas instrucciones básicas y vínculos a herramientas que pueden ser de ayuda en las primeras etapas de la evaluación.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Paso 1: Desarrollar una comprensión básica de los escenarios de datos personales de su organización 

Debe evaluar la exposición a los riesgos de privacidad de datos en función del tipo de datos personales que administra actualmente, dónde se almacenan, qué controles de protección se colocan en ellos, cómo se administra su ciclo de vida y quién tiene acceso a ellos. 

Como punto de partida, es importante realizar un inventario de los tipos de datos personales que existen en su entorno de Microsoft 365. Use estas categorías:

- Datos de empleados necesarios para llevar a cabo funciones empresariales diarias
- Datos que la organización tiene sobre sus clientes empresariales, socios y otras relaciones en el escenario de negocio a negocio (B2B).
- Datos que la organización tiene sobre los consumidores que proporcionan información a los servicios en línea que administra la organización en el escenario de negocio a cliente (B2C).

Este es un ejemplo de los distintos tipos de datos para los departamentos típicos de una organización.

![Tipos de datos personales](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Gran parte de los datos personales que están sujetos a la regulación de privacidad de datos normalmente se recopilan y almacenan fuera de Microsoft 365. Los datos personales de aplicaciones móviles o web orientadas al consumidor tendrían que haber sido exportados de dichas aplicaciones a Microsoft 365 para estar sujetos al examen de privacidad de datos en Microsoft 365. 

La exposición a la privacidad de datos en Microsoft 365 puede ser más limitada en relación con las aplicaciones web y los sistemas CRM, lo que esta solución no aborda.

También es importante tener en cuenta los siguientes desafíos comunes de cumplimiento de privacidad de datos al evaluar su perfil de riesgo:

 - **Distribución de datos personales.** ¿Qué tan dispersa es la información sobre un tema determinado? ¿Es lo suficientemente conocido como para convencer a los organismos reguladores de que hay controles adecuados? ¿Se puede investigar y corregir si es necesario?
- **Protección contra la exfiltración.** ¿Cómo proteger los datos personales de un tipo u origen determinados para que no se vea comprometidos y cómo responder si lo fueron?
- **Protección frente a riesgos.** ¿Qué mecanismos de protección de la información son adecuados en relación con el riesgo y cómo mantener la continuidad y productividad del negocio y minimizar el impacto del usuario final si se requiere la intervención del usuario final? Por ejemplo, ¿se debe usar la clasificación manual o el cifrado?
- **Retención de datos personales.** ¿Cuánto tiempo debe mantenerse la información que contiene datos personales por motivos empresariales válidos y cómo evitar prácticas anteriores de mantenimiento para siempre, equilibradas con las necesidades de retención para la continuidad empresarial?
- **Control de solicitudes de interesados.** ¿Qué mecanismos se necesitan para controlar las solicitudes de interesados (DSR) y las acciones correctivas, como anonimización, reacción y eliminación?
- **Supervisión e informes continuos.** ¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los distintos tipos de datos y orígenes?
- **Limitaciones en el procesamiento de datos.** ¿Existen limitaciones en el uso de datos para la información recopilada o almacenada a través de estos métodos que la organización debe reflejar en los controles de privacidad? Por ejemplo, los compromisos de que el personal de ventas no usará datos personales pueden requerir que su organización ponga en marcha mecanismos para evitar la transferencia o el almacenamiento de esa información en sistemas asociados con la organización de ventas.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Datos de empleados necesarios para llevar a cabo funciones empresariales diarias

Por naturaleza, las organizaciones necesitan recopilar datos sobre los empleados con fines de identidad electrónica y recursos humanos, en función de lo que acepten en sus contratos de empleados. Siempre que una persona trabaje para una empresa, esto no suele ser un problema. Es posible que la organización desee poner en marcha mecanismos para evitar que actores malintencionados exfiltran o filtre datos personales de los empleados. 

Si una persona deja una empresa, las organizaciones suelen tener procesos, procedimientos y programaciones de retención y eliminación para quitar cuentas de usuario, retirar buzones y unidades personales, y cambiar el estado de los empleados en aspectos como los sistemas de recursos humanos. En situaciones en las que haya litigios, un empleado u otra parte en una investigación legal puede tener razones válidas para obtener información sobre datos personales almacenados en los sistemas de la organización. En algunas ocasiones, esa parte puede solicitar que dichos datos se eliminen o anonimizar. 

Para satisfacer estas necesidades, las organizaciones deben tener procesos y procedimientos que atendrán a las necesidades preventivas, de investigación y correctivas para facilitar dichas solicitudes, y deben tener en cuenta que cierta información sobre un empleado puede considerarse razonablemente crucial para la continuidad empresarial. Por ejemplo, información en la que una persona ha escrito un archivo o ha realizado una función. 

>[!Note]
>Para obtener técnicas de investigación y corrección para datos personales en Microsoft 365, vea el artículo [de supervisión y respuesta.](information-protection-deploy-monitor-respond.md) Es posible que también desee usar esquemas automatizados de clasificación y protección para asegurarse de que los datos personales se controlan dentro de la organización, así como evitar que abandonen la organización en situaciones de actor malintencionado. Vea el [artículo de protección de información](information-protection-deploy-protect-information.md) para obtener más información.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Datos que la organización tiene sobre sus clientes empresariales en el escenario B2B

La recopilación de información B2B también es un desafío porque es posible que su organización tenga que mantener registros de los nombres de los clientes y las transacciones en sus distintos sistemas con fines de continuidad empresarial, pero proteger esa información de la filtración inadvertida o malintencionada. Al igual que los datos de los empleados, las organizaciones deben tener directivas, procedimientos y controles técnicos para proteger dichos datos, así como la antigüedad según las programaciones definidas de retención y eliminación. 

Normalmente, los contratos con clientes externos, socios y otras entidades con las que la organización hace negocios tendrán lenguaje que aborda el tratamiento de estos datos, incluida la protección, retención y eliminación tanto durante como después de que la entidad tenga una relación con la organización. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Datos que la organización tiene sobre los consumidores que proporcionan información a los servicios en línea que administra la organización en el escenario B2C

Esta categoría es la que más piensa la gente para la privacidad de los datos, debido a muchas instancias públicas de pérdida de datos de clientes. Esto puede ser intencionado, como un tercero bajo contrato con el proveedor, o no intencionado, como la filtración por parte de un actor malintencionado. La protección de datos de los consumidores es uno de los principales motivos por los que la UE y otras organizaciones aprobaron estas normativas. Las normativas de privacidad de datos como RGPD y CCPA requieren que realices la planeación de:

- [Planes de acción](../compliance/gdpr-action-plan.md) y [listas de comprobación de preparación de responsabilidad](../compliance/gdpr-arc-office365.md)
- [Evaluaciones del impacto en la protección de datos](../compliance/gdpr-data-protection-impact-assessments.md)
- [Notificaciones de infracciones](../compliance/gdpr-breach-office365.md)
- [Solicitudes de interesados](../compliance/gdpr-dsr-office365.md)

Si su organización no realiza una gran cantidad de recopilación directa de datos del consumidor, esta categoría puede ser menos un problema. Sin embargo, es posible que deba seguir los procesos descritos en estos artículos para lograr el cumplimiento.

### <a name="step-1-summary"></a>Resumen del paso 1

Comprender su exposición a la regulación de riesgos y privacidad de datos es un primer paso importante que se basa en una comprensión básica de los escenarios de datos personales de su organización.

Si no tiene datos personales de los consumidores en su entorno de Microsoft 365 o se limita a determinadas partes del entorno y la necesidad de un control técnico se basa en que existe una exposición de datos de tipo consumidor, es posible que ese control técnico solo deba emplearse en partes de alto riesgo del entorno, no en todas partes.

Aunque una organización externa o una recomendación de conjunto de controles estándar, como el Administrador de cumplimiento de Microsoft 365, pueden ayudar a informar a su estrategia de control, su elección de implementación debe estar controlada por el reconocimiento del inventario de datos para cuantificar la exposición real a riesgos.

La mayoría de las organizaciones tendrán alguna exposición a uno de los escenarios anteriores. Es importante adoptar un enfoque holístico de la evaluación.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Paso 2: Evaluar su preparación para cumplir con las normativas de privacidad de datos

Aunque son específicas del RGPD, las preguntas que se plantea en la herramienta gratuita de evaluación del RGPD de [Microsoft](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) proporcionan un buen comienzo para comprender la preparación general de la privacidad de los datos. 

Las organizaciones sujetas a otras normativas de privacidad de datos, como la CCPA en Los Estados Unidos o lgPD de Brasil, también pueden beneficiarse del inventario de preparación de esta herramienta debido a disposiciones superpuestas con el RGPD.

La evaluación del RGPD consta de estas secciones:

| Section | Description |
|:-------|:-----|
| Gobierno | <ol><li>¿La directiva de privacidad especifica explícitamente qué información de datos se está procesando? </li><li>¿Ejecuta periódicamente evaluaciones de impacto en la privacidad (PIA)? </li><li> ¿Usa una herramienta para administrar la información personal (PI)? </li><li> ¿Tiene autoridad legal para llevar a cabo negocios con datos de PI de una persona determinada? ¿Realiza un seguimiento del consentimiento de los datos? </li><li> ¿Realiza un seguimiento, implementa y administra los controles de auditoría? ¿Supervisa las pérdidas de datos? </li></ol>|
| Eliminación y notificación | <ol><li>¿Proporciona instrucciones explícitas sobre cómo se puede acceder a los datos de los usuarios? </li><li> ¿Tiene procesos documentados para administrar el consentimiento de no participar? </li><li> ¿Tiene un proceso de eliminación automatizada de datos? </li><li>   ¿Tiene un proceso para validar la identidad al interactuar con un cliente? </li></ol>|
| Mitigación de riesgos y seguridad de la información | <ol><li>¿Usa herramientas para examinar datos no estructurados? </li><li>¿Todos los servidores están actualizados y usa firewalls para protegerlos? </li><li>¿Ejecuta copias de seguridad periódicas de los servidores? </li><li>¿Supervisa activamente las pérdidas de datos? </li><li>¿Cifra los datos en reposo y en transmisión? </li></ol>|
| Administración de directivas | <ol><li>¿Cómo se administran las reglas corporativas de enlace (BCR)? </li><li>¿Realiza un seguimiento del consentimiento de los datos? </li><li> En una escala de 1 a 5, ¿los contratos cubren por completo las clasificaciones de datos y los requisitos de control? </li><li>¿Tiene y prueba periódicamente un plan de respuesta a incidentes? </li><li>¿Qué directiva usa para administrar el acceso? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Paso 3: Identifique los tipos de información confidencial que se producen en su entorno de Microsoft 365. 

Este paso implica la identificación de determinados tipos de información confidencial que están sujetos a controles normativos específicos, así como la aparición de estos en su entorno de Microsoft 365. 

Encontrar contenido en su entorno que contenga contenido personal puede ser una tarea muy compleja, que anteriormente implicaba una combinación de uso de búsqueda de cumplimiento, exhibición de documentos electrónicos, exhibición avanzada de documentos electrónicos, DLP y auditoría. 

Con la  nueva solución de clasificación de datos en el [](../compliance/data-classification-content-explorer.md) Centro de administración de cumplimiento de Microsoft, esto se ha vuelto mucho más fácil con la funcionalidad Explorador de contenido, que funciona con tipos de información confidencial integrados o personalizados, incluidos los relacionados con datos personales.
 
### <a name="sensitive-information-types"></a>Tipos de información confidencial

El Centro de administración de cumplimiento de Microsoft viene cargado previamente con más de 100 tipos de información confidencial, la mayoría de ellos relacionados con la identificación y la localización de datos personales. Estos tipos de información confidencial integrados pueden ayudar a identificar y proteger números de tarjeta de crédito, números de cuentas bancarias, números de pasaporte y mucho más, en función de los patrones definidos por una expresión regular (regex) o una función. Para obtener más información, consulte [Qué buscan los tipos de información confidencial](../compliance/what-the-sensitive-information-types-look-for.md).

Si necesita identificar y proteger un tipo regional o específico de la organización de elementos confidenciales, como un formato personalizado para los id. de empleado u otra información personal que aún no está cubierta por un tipo de información confidencial integrado, puede crear un tipo de información confidencial personalizado con estos métodos: 

- PowerShell
- Reglas personalizadas con coincidencia exacta de datos (EDM)
- A través de la interfaz de usuario de administración del Centro de cumplimiento, como se resalta en el artículo [Puntuación](information-protection-deploy-compliance.md) de cumplimiento de uso y Administrador de cumplimiento

También puede personalizar un tipo de información confidencial integrado existente.

Vea estos artículos para obtener más información:

- [Personalizar un tipo de información confidencial integrado](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Más información sobre los tipos de información confidencial](../compliance/sensitive-information-type-learn-about.md)
- [Crear un tipo de información confidencial personalizado en el Centro de seguridad y cumplimiento](../compliance/create-a-custom-sensitive-information-type.md)
- [Crear un tipo personalizado de información confidencial en PowerShell del Centro de seguridad y cumplimientol](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Explorador de contenido

Una herramienta importante que para determinar la aparición de [](../compliance/data-classification-content-explorer.md) elementos confidenciales en su entorno es el nuevo Explorador de contenido en el Centro de administración de cumplimiento de Microsoft 365. Es una herramienta automatizada para el examen inicial y continuo de toda la suscripción de Microsoft 365 para la aparición de tipos de información confidencial y la visualización de los resultados.
 
La nueva herramienta Explorador de contenido le permite identificar rápidamente las ubicaciones de los elementos confidenciales en su entorno, mediante tipos integrados de información confidencial o personalizados. Esto puede implicar el establecimiento de un proceso y la responsabilidad asignada de investigar periódicamente la presencia y la ubicación de elementos confidenciales.

Junto con los otros pasos resaltados en este artículo, esto proporciona un punto de partida para identificar la exposición general de riesgos, la preparación y la ubicación de los elementos confidenciales para proteger mediante la configuración y supervisión planeadas de Microsoft 365. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Otros métodos para identificar datos personales en su entorno

Además del Explorador de contenido, las organizaciones tienen acceso a la capacidad de búsqueda de contenido para producir búsquedas personalizadas para buscar datos personales en su entorno, mediante criterios de búsqueda avanzados y filtros personalizados.

En este artículo se proporcionan instrucciones detalladas sobre el uso de la búsqueda de contenido para la detección [de datos personales.](../compliance/search-for-and-find-personal-data.md) La búsqueda de contenido y otras técnicas de detección también se exploran en [las DSR para el RGPD y la CCPA.](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)

En el artículo de supervisión y respuesta se proporcionan información adicional sobre técnicas de investigación y corrección para datos [personales en](information-protection-deploy-monitor-respond.md)Microsoft 365.
