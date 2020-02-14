---
title: 'Reglamento general de protección de datos '
description: Directrices técnicas de Microsoft en relación con el Reglamento general de protección de datos (RGPD)
keywords: Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
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
ms.openlocfilehash: f7c2a19a58dd616e2516ea70492f4f65ab211441
ms.sourcegitcommit: 2498cd4af90c31771167a1be9f8f12a96dc6500f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41916885"
---
# <a name="general-data-protection-regulation-summary"></a>Resumen del reglamento general de protección de datos 

El reglamento general de protección de datos (RGPD), añade nuevas normas organizaciones que ofrecen bienes y servicios a los ciudadanos de la Unión Europea (UE), o que recopilen y analicen datos de los residentes de la UE, sin importar donde estén ubicados usted o su empresa. Este documento lo guiará a información que le ayude a respetar los derechos y cumplir las obligaciones del reglamento general de protección de datos, al usar los productos y servicios de Microsoft. Un [plan de acción recomendado para el reglamento general de protección de datos](gdpr-action-plan.md)y[listas de comprobación de responsabilidad](gdpr-arc.md)proporcionan recursos adicionales para evaluar e implementar el cumplimiento del reglamento general de protección de datos.

## <a name="terminology"></a>Terminología

Definiciones útiles de los términos del RGPD utilizados en este documento:

- **Controlador de datos (controlador)**: una persona jurídica, autoridad pública, agencia u otro organismo, que por sí solos o conjuntamente con otras personas, determinan el propósito y el medio del procesamiento de datos personales.  
- **Datos personales  e interesado**: cualquier información relacionada con una persona física identificada o una persona natural identificable (interesado), una persona física identificable es la que puede identificarse, directa o indirectamente.  
- **Procesador**: una persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.  
- **Datos de clientes**: Datos producidos y almacenados en las operaciones diarias de su empresa.

## <a name="what-is-the-gdpr"></a>¿Qué es el RGPD?

El reglamento general de protección de datos (RGPD) otorga derechos a los usuarios para administrar los datos personales recopilados por una organización. Estos derechos se pueden ejercer a través de una solicitud de temas de datos (STD). La organización debe proporcionar información puntual sobre DSR y violaciones de datos, y llevar a cabo evaluaciones de impacto de la protección de datos (EIPA).

Se deben tener en cuenta varios puntos al implementar o evaluar requisitos del Reglamento General de Protección de Datos (RGPD):

- Desarrollando o evaluando la Directiva de privacidad de los datos de cumplimiento normativo del reglamento general de protección de datos (RGPD).
- Evaluar la seguridad de los datos de su organización.
- ¿Quién es su controlador de datos?
- ¿Qué procesos de seguridad de datos tiene que llevar a cabo?

El[plan de acción recomendado para el reglamento general de protección de datos (RGPD)](gdpr-action-plan.md) y [el control en las listas de comprobación](gdpr-arc.md)pueden conducir a tener un pensamiento adicional puntual.

Las siguientes tareas están relacionadas con el cumplimiento de los estándares del reglamento general de protección de datos (RGPD). Siga los vínculos de la lista para obtener más información sobre la implementación.  

- **[Solicitudes de temas de datos (STD)](gdpr-data-subject-requests.md)**. Una solicitud formal de datos, sujetos a un controlador para realizar una acción (cambiar, restringir, acceder) en sus datos personales. 
- **[Notificación de infracciones](gdpr-breach-notification.md)**. Según el reglamento general de protección de datos (RGPD), una infracción de datos personales es "una infracción de seguridad que se traduce en la destrucción accidental o ilegal, la pérdida, la modificación, la divulgación no autorizada o el acceso a datos personales transmitidos, almacenados o procesados de alguna forma".
- **[ Evaluación de impacto de la protección de datos (EPIA)](gdpr-data-protection-impact-assessments.md)**. Los controladores de datos son requeridos en el reglamento general de protección de datos (RGPD), para preparar una evaluación de impacto de la protección de datos (EIPA) para las operaciones de datos que sean "probables que resulten en un alto riesgo para los derechos y libertades de las personas naturales".

Como se ha mencionado anteriormente, el plan de acción recomendado para las listas de comprobación de la preparación de el reglamento general de protección de datos (RGPD), y el control en las listas de comprobación ofrece una guía de conformidad para implementar o evaluar el reglamento general de protección de datos (RGPD), con los productos y servicios de Microsoft.

## <a name="the-gdpr-in-action"></a>El reglamento general de protección de datos (RGPD) en acción

En esta sección se proporcionan un esquema y un enfoque para completar las tareas del reglamento general de protección de datos (RGPD) mencionadas anteriormente. La realización de estas tareas puede variar en función de la configuración de Microsoft.

### <a name="data-subject-request-dsr"></a>Solicitud de temas de datos (STD).

El RGPD concede a las personas (o interesados) determinados derechos en relación con el procesamiento de sus datos personales, incluido el derecho a corregir datos inexactos, borrar datos o restringir su procesamiento, recibir sus datos y cumplimentar una solicitud para transmitirlos a otro responsable del tratamiento. El controlador es responsable de proporcionar a tiempo una respuesta coherente del reglamento general de protección de datos (RGPD). Para obtener información técnica, consulte [Solicitudes de temas de datos](gdpr-data-subject-requests.md).  

#### <a name="dsr-faqs"></a>Preguntas frecuentes sobre STD

**¿Qué medidas serán necesarias para completar una solicitud de temas de datos (STD)?**

Una STD implica seis actividades: descubrir, obtener acceso, rectificar, limitar, exportar y eliminar.

**¿Cuáles son los orígenes de datos?**

Una gran parte de los datos de la organización se generan en[las aplicaciones de Office](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) como Excel y Outlook.  Es posible que también encuentre información relevante para una solicitud de temas de datos (STD) en[opciones](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) generadas por productos y servicios de Microsoft, y[ registros](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)generados por el sistema.

**¿Qué tipos de datos debe buscar?**

Es posible que los datos personales se encuentren en datos de clientes, opciones generadas por productos y servicios de Microsoft y registros generados por el sistema.

**¿Cómo se buscarán los datos personales?**

La búsqueda de datos personales puede variar entre todos los productos y servicios de Microsoft. Las herramientas de búsqueda incluyen las capacidades [búsqueda de contenido](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) o [búsqueda en aplicación](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs). Los administradores pueden tener acceso[a los registros generados por el sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)asociados a la actividad de un usuario.  

**¿En que formato debería estar disponible la información personal?**

El reglamento general de protección de datos (RGPD) "derecho de portabilidad de datos" permite temas de datos para solicitar una copia electrónica de sus datos personales en un "formato estructurado, común y legible", y solicitar que su organización transmita estos archivos a otro controlador de datos. 

**¿Qué exige el RGPD y cuáles son mis obligaciones como responsable del tratamiento?**

Como responsable del tratamiento, el RGPD le exige que sea capaz de:

- Proporcionar a los interesados una copia de sus datos personales, junto con una explicación de la categoría de los datos que se procesan, los fines del procesamiento y las categorías de terceros a quienes es posible que se revelen sus datos.
- Ayudar a todas y cada una de las personas a ejercer su derecho a corregir datos personales inexactos, borrar datos o restringir su procesamiento, recibir sus datos en un formato legible y, si procede, cumplimentar una solicitud para transmitirlos a otro responsable del tratamiento.


**¿Qué exige el RGPD y cuáles son las responsabilidades de Microsoft como encargado del tratamiento?**

Hemos de implementar las medidas técnicas y organizativas adecuadas para ayudarle a responder a las solicitudes de los interesados en el ejercicio de sus derechos, tal y como se ha descrito antes.

**¿Dónde puedo encontrar información relacionada con RGPD para servidores locales?**

Puede encontrar una serie de artículos relacionados con el RGPD aquí. Elaborados por Microsoft, proporcionan métodos recomendados para cargas de trabajo local de SharePoint Server, Exchange Server, Project Server, Office Web Apps Server, Office Online Server y archivos compartidos locales.

**¿Cómo le permite Microsoft responder a las solicitudes de los interesados?**

Los servicios en línea ofrecen innumerables funcionalidades que le permiten, como responsable del tratamiento, dar respuesta a una solicitud de los interesados. Los controles administrativos y los servicios en línea de Microsoft le ayudan a actuar sobre datos personales que responden a solicitudes de derechos de interesados, lo que le permite detectar, tener acceso a, rectificar, restringir y exportar datos personales que residen en los datos administrados por responsables del tratamiento que se almacenan en la nube de Microsoft.
 Los servicios en línea también proporcionan datos en formato de lectura mecánica cuando lo necesite.

### <a name="data-protection-impact-assessment"></a>Evaluaciones de impacto de protección de datos

De acuerdo con el reglamento general de protección de datos (RGPD), los controladores de datos son requeridos para preparar una[evaluación de impacto de la protección de datos ](gdpr-data-protection-impact-assessments.md)(EPIA) para procesar operaciones que sean "probables que resulten en un alto riesgo para los derechos y libertades de las personas naturales". No hay nada inherente a los productos y servicios de Microsoft que necesitan la creación de un evaluación de impacto de la protección de datos (EIPA). En su lugar, depende de los detalles de la configuración de Microsoft. Encontrará una lista de los detalles que debe considerar de Office en [Contenido de la evaluación de impacto de la protección de datos (EIPA)](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)

#### <a name="dpia-faqs"></a>Preguntas frecuentes sobre EIPA

**¿Cuándo debería llevar a cabo una evaluación de impacto de la protección de datos (EIPA)?**

Los controladores son necesarios para realizar una evaluación de impacto de la protección de datos (EIPA), solucionar problemas de seguridad de datos personales o como resultado de una infracción de datos. Se tratan ejemplos específicos de factores de riesgo en Office [para determinar si se necesita una evaluación de impacto de la protección de datos (EIPA)](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed).  

**¿Qué se necesita para elaborar una EIPA?**

El reglamento general de protección de datos (RGPD) ordena que una evaluación de impacto de la protección de datos (EIPA) incluya:

- Una evaluación de la necesidad y proporcionalidad del procesamiento de datos en relación con el propósito de la evaluación de impacto de la protección de datos.
- Una evaluación de los riesgos para los derechos y libertades de los temas de los datos
- Las medidas previstas para abordar los riesgos, las protecciones, las medidas de seguridad y los mecanismos para asegurar la protección de los datos personales y demostrar el cumplimiento de el reglamento general de protección de datos (RGPD).

**¿Cuáles son mis obligaciones como responsable del tratamiento?**

En el RGPD, como responsable del tratamiento está obligado a realizar las EIPA antes del procesamiento de datos que pueda derivarse en un alto riesgo para los derechos y las libertades de las personas, en particular, el procesamiento con nuevas tecnologías. El RGPD proporciona la siguiente lista no exhaustiva de los casos en que deben realizarse evaluaciones EIPA:

- Procesamiento automatizado con el fin de crear perfiles y realizar actividades similares que tengan efectos legales o afecten significativamente a los interesados;  
- Procesamiento a gran escala de categorías especiales de datos personales (datos que revelan el origen étnico o racial, las opiniones políticas y similares) o de datos relativos a delitos y condenas penales;  
- Supervisión sistemática a gran escala de un área de acceso público.  

El RGPD exige además que se consulte a la autoridad de protección de datos (DPA) antes de comenzar cualquier procesamiento si no se pueden identificar suficientes procesos que minimicen los riesgos altos para los interesados.

**¿Cuáles son las responsabilidades de Microsoft?**

Microsoft practica la privacidad por diseño y la privacidad de forma predeterminada en sus funciones de ingeniería y negocios.
 En el marco de estas iniciativas, Microsoft realiza revisiones completas de privacidad de las operaciones de procesamiento de datos que tienen posibilidades de afectar a los derechos y las libertades de los interesados. Los equipos de privacidad integrados en los grupos de servicios revisan el diseño y la implementación de los servicios para asegurarse de que los datos personales se procesan de manera respetuosa acorde a la legislación internacional, las expectativas de los usuarios y nuestros compromisos explícitos.

Estas revisiones de privacidad tienden a estar pormenorizadas (es posible que un servicio concreto sea objeto de docenas o centenares de revisiones). 
 Microsoft recoge estas revisiones de privacidad pormenorizadas en evaluaciones del impacto en la protección de datos (EIPA) que cubren las principales agrupaciones de procesamiento, que luego revisa el responsable de protección de datos (DPO) de la UE de Microsoft. El DPO evalúa los riesgos relacionados con el procesamiento de datos para asegurarse de que existen suficientes circunstancias atenuantes. Si el DPO encuentra riesgos sin mitigar, recomienda modificaciones al grupo de ingeniería. Las EIPA se revisarán y actualizarán de acuerdo con los cambios en los riesgos de protección de datos.


Como encargado del tratamiento, Microsoft tiene la obligación de asistir a los responsables del tratamiento en garantizar el cumplimiento de los requisitos de EIPA establecidos en el RGPD. Para apoyar a nuestros clientes, se extraen las secciones pertinentes de las EIPA de Microsoft, que se ofrecerán a través de esta sección en futuras actualizaciones, con la intención de permitir que los responsables del tratamiento cuenten con los servicios de Microsoft para aprovechar los extractos y crear sus propias DPIA.

### <a name="breach-notification"></a>Notificación de infracciones

El RGPD impone requisitos de notificación a los responsables del tratamiento y a los encargados del tratamiento en caso de vulneración de datos personales. Al ser un procesador de datos, Microsoft garantiza que los clientes pueden cumplir los requisitos de notificación de incumplimiento del reglamento general de protección de datos (RGPD). Los controladores de datos son responsables de evaluar los riesgos relacionados con la privacidad de los datos y determinar si una vulneración requiere la notificación a la DPA de un cliente. Microsoft proporciona la información necesaria para realizar la evaluación. Para obtener más información sobre cómo Microsoft detecta y responde ante una violación de datos personales, en[Notificación de violación de datos según el reglamento general de protección de datos (RGPD)](gdpr-breach-notification.md).

#### <a name="breach-notification-faqs"></a>Preguntas frecuentes sobre notificación de infracciones

**¿Qué constituye una vulneración de datos personales en virtud del RGPD?**

Los datos personales se refieren a cualquier información relacionada con un usuario individual que pueda usarse para identificarlo directa o indirectamente. Una vulneración de datos personales es "una vulneración de seguridad que se traduce en la destrucción accidental o ilegal, pérdida, modificación, divulgación no autorizada o acceso a datos personales transmitidos, almacenados o procesados de alguna otra forma".

**¿Cuáles son sus obligaciones como responsable del tratamiento?**

Si se produjera una vulneración de datos personales que pueda derivarse en un riesgo alto para los derechos y las libertades de las personas (tales como discriminación, robos de identidad, fraude, perjuicio financiero o daños a su reputación), el RGPD exige que usted:

- Se notifique a la correspondiente autoridad de protección de datos (DPA) en las 72 horas siguientes tener conocimiento de ello; por ejemplo, después de que Microsoft se lo notifique. Si no notifica a la DPA en ese intervalo de tiempo, tendrá que darle explicaciones. Este aviso a la DPA es obligatorio aunque no sea probable que el riesgo para las personas derive en alto riesgo.
- Notifique la vulneración a los interesados sin dilación.
- La documentación de la vulneración incluye una descripción de la naturaleza de la misma como, por ejemplo, cuantas personas se han visto afectadas, el número de registros afectados, las consecuencias de la vulneración y cualquier acción correctiva que su organización proponga o tome.

**¿Cuáles son las responsabilidades de Microsoft como encargado del tratamiento?**

El RGPD exige que, tras tener conocimiento de una vulneración de datos personales, lo notifiquemos a usted sin la menor dilación. Cuando Microsoft sea el encargado del tratamiento de datos, nuestras obligaciones reflejarán tanto los requisitos del RGPD como nuestras disposiciones contractuales estándar en todo el mundo. Se considera que todas las vulneraciones de datos quedan dentro del ámbito de aplicación; no hay riesgo de umbral de perjuicio. Notificaremos a nuestros clientes si la vulneración de datos ha afectado directamente a Microsoft o a algunos de nuestros subencargados del tratamiento. Contamos con procesos para identificarlas rápidamente y ponerse en contacto con el personal de incidentes de seguridad que ha identificado en la organización. Además, todos los subencargados del tratamiento están obligados por contrato a informar de sus propias vulneraciones a Microsoft y ofrecer garantías al respecto.

**¿Cómo detectará Microsoft una vulneración de datos?**

Todos nuestros servicios y personal siguen procedimientos internos de administración de incidentes para asegurarnos de que tomamos precauciones adecuadas para evitar las vulneraciones de datos desde el primer momento. Pero, además, los servicios en línea de Microsoft tienen controles de seguridad específicos en todas nuestras plataformas para detectar vulneraciones de datos en el caso poco probable de que se produzcan.

**¿Cómo responderá Microsoft a una vulneración de datos?**

Para apoyarle en una vulneración de datos personales, Microsoft cuenta con:
    - Personal de seguridad especializado en los procedimientos concretos que hay que seguir.
    - Directivas, procedimientos y controles para garantizar que Microsoft mantiene registros detallados. Esta respuesta incluye documentación que captura la información del incidente, sus efectos y la acción correctiva, así como el seguimiento y almacenamiento de la información en nuestros sistemas de administración de incidentes.

**¿Cómo me notificará Microsoft en caso de una vulneración de datos?**

Microsoft cuenta con directivas y procedimientos para notificarle inmediatamente. Para que cumpla los requisitos de notificación a la DPA, le proporcionaremos una descripción del proceso que usamos para determinar si se ha producido una vulneración de datos personales, una descripción de la naturaleza de la vulneración y una descripción de las medidas que tomamos para mitigar sus efectos.

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>Listas de comprobación de preparación de responsabilidad para el reglamento general de protección de datos (RGPD)

Estas [listas de comprobación](gdpr-arc.md)proporciona una forma cómoda de obtener acceso a la información que puede necesitar para respaldar el reglamento general de protección de datos (RGPD) al usar los productos de Microsoft. Los elementos de en la lista de control se podrán administrar con la[ puntuación de cumplimiento Microsoft](compliance-score.md) haciendo referencia al identificador y título de control encontrados en los controles administrados por el cliente en el icono del RGPD.

## <a name="gdpr-faqs"></a>Preguntas frecuentes sobre el RGPD

**¿Microsoft realiza compromisos con sus clientes en lo que respecta al RGPD?**

Sí. El RGPD exige que los responsables (como las organizaciones que usan los servicios empresariales en línea de Microsoft) solo utilicen encargados (como Microsoft) que ofrezcan garantías suficientes para cumplir con los requisitos clave del RGPD. Microsoft ha dado un paso proactivo al proporcionar estos compromisos a todos los clientes de licencias por volumen como parte de sus acuerdos.

**¿Cómo me ayuda Microsoft a cumplir?**

Microsoft proporciona herramientas y documentación para darle soporte en su responsabilidad respecto del RGPD. Esto incluye soporte técnico a los derechos de los interesados de los datos, realización propia de evaluaciones de impacto en la protección de datos y trabajo conjunto para resolver infracciones de datos personales.

**¿Qué compromisos hay en los Términos de RGPD?**

Los Términos de RGPD de Microsoft reflejan los compromisos requeridos al encargado del tratamiento en el artículo 28. El artículo 28 exige que los encargados del tratamiento se comprometan a:

- Acudir a subprocesadores solo con el consentimiento del controlador y ser responsable por los subprocesadores.
- Procesar los datos personales solo de acuerdo con las instrucciones del controlador, incluido lo relativo a las transferencias.
- Asegurarse de que las personas que procesan los datos personales estén comprometidas con la confidencialidad.
- Implementar medidas técnicas y organizativas adecuadas para asegurar un nivel de seguridad de los datos personales adecuado al riesgo.
- Asistir a los controladores en sus obligaciones para responder a las solicitudes de los interesados para ejercer sus derechos en virtud del RGPD.
- Cumplir con los requisitos de notificación y asistencia en infracciones.
- Asistir a los controladores con evaluaciones de impacto en la protección de datos y consulta con autoridades supervisoras.
- Eliminar o devolver datos personales al final de la prestación de servicios.
- Prestar soporte al controlador con evidencia de que cumple con el RGPD.

**¿Sobre qué base facilita Microsoft la transferencia de datos personales fuera de la Unión Europea?**

Microsoft aplica desde hace largo tiempo las cláusulas contractuales estándar (también conocidas como las cláusulas modelo) como base para la transferencia de datos para sus servicios en línea para empresas. Las cláusulas contractuales estándar son términos estándar proporcionadas por la Comisión Europea que pueden usarse para transferir datos fuera del Espacio Económico Europeo de manera apropiada. Microsoft ha incorporado las cláusulas contractuales estándar en todos nuestros contratos de licencias por volumen mediante los [términos de servicios en línea](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). El grupo de trabajo del artículo 29 ha detectado que la implementación por parte de Microsoft de las cláusulas contractuales estándares es apropiada. Además, cuando Privacy Shield entre EE. UU. y la UE estuvo disponible, Microsoft fue la primera empresa en obtener certificación. Consulte la [certificación de Microsoft en Privacy Shield](https://www.privacyshield.gov/participant?id=a2zt0000000KzNaAAK&status=Active) y lea los [términos de los servicios en línea](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). Privacy Shield permite a los clientes que deseen transferir sus datos al estadounidense hacerlo de manera coherente con las obligaciones en materia de protección de datos.

**¿Qué más ofrece Microsoft en materia de cumplimiento?**

Como empresa global con clientes en casi todos los países del mundo, Microsoft tiene un sólido conjunto de recursos de cumplimiento para asistir a nuestros clientes. Para ver una lista completa de nuestra oferta en materia de cumplimiento, que incluye FedRamp, HIPAA/HITECH, ISO 27001, ISO 27002, ISO 27018, NIST 800-171, UK G-Cloud y muchas otras, visite nuestros [temas de la oferta de cumplimiento](offering-home.md).

**¿Cómo afectará el RGPD a mi empresa?**

El RGPD impone una amplia variedad de requisitos a las organizaciones que recopilan o procesan datos personales, incluido el requisito de cumplir con seis principios clave:

- *Transparencia*, *equidad* y *legitimidad* en el manejo y uso de datos personales. Deberá ser claro con las personas sobre cómo se usan los datos personales y también necesitará una "base legítima" para procesar dichos datos.
- Limitar el procesamiento de datos personales a los propósitos *especificados*, *explícitos* y *legitimados*. No podrá volver a usar ni revelar datos personales para propósitos que no sean "compatibles" con el propósito para el que los datos se recopilaron originalmente.
- *Minimizar la recogida y el almacenamiento de datos personales* hasta lo apropiado y relevante para la finalidad prevista.
- Asegurar la *precisión de los datos personales* y permitir que sean *eliminados o rectificados*. Tendrá que tomar medidas para asegurarse de que los datos personales que contiene son precisos y se pueden corregir si se producen errores.
- *Limitar el almacenamiento de datos personales*. Deberá asegurarse de que los datos personales se conserven solo durante el tiempo necesario para lograr el propósito para el que se recopilan los datos.
- Garantizar la *seguridad*, la *integridad* y la *confidencialidad de los datos personales*. Su organización debe realizar las acciones necesarias para proteger los datos personales con medidas de seguridad técnicas y organizacionales.

Deberá comprender cuáles son las obligaciones específicas de su organización con respecto al RGPD y cómo cumplirlas, aunque Microsoft está aquí para ayudarle en su proceso de cumplimiento con el RGPD.

**¿Qué derechos deben habilitar las empresas en relación con el RGPD?**

El RGPD ofrece a los residentes de la UE control sobre sus datos personales a través de un conjunto de derechos de los «interesados». Aquí se incluyen los derechos siguientes:

- Acceso a información acerca de cómo se usan los datos personales.
- Acceso a los datos personales conservados por una organización.
- Eliminación o corrección de datos personales incorrectos.
- Rectificación y eliminación de datos personales en determinadas circunstancias (también denominado «derecho al olvido»).
- Restricciones u objeciones al procesamiento automatizado de los datos personales.
- Recibir una copia de los datos personales (portabilidad).

**¿Quiénes son los Procesadores y los Controladores?**

Un controlador es una persona física o jurídica, una autoridad pública, una agencia u otro organismo que, solo o junto con otros, determina los medios de procesamiento de los datos personales y sus fines. Un procesador es una persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.

**¿Se aplica el RGPD a los procesadores y controladores?**

Sí, el RGPD se aplica a los controladores y los procesadores. Los controladores solo deben recurrir a procesadores que adopten medidas para cumplir con los requisitos del RGPD. De acuerdo con el RGPD, los procesadores se enfrentan a obligaciones y responsabilidad adicionales en relación con el incumplimiento, o por acciones emprendidas al margen de las instrucciones proporcionadas por el controlador en relación con la Directiva de protección de datos. Las tareas del procesador incluyen, sin limitación, las siguientes:

- Procesar los datos únicamente según las instrucciones del controlador.
- Hacer uso de las medidas técnicas y organizativas adecuadas para proteger los datos personales.
- Colaborar con el controlador en relación con solicitudes de los interesados.
- Garantizar que los subprocesadores se comprometen con estos requisitos.

**¿A cuánto pueden ascender las multas a las empresas por incumplimiento?**

Las empresas pueden tener multas de hasta 20 millones de euros o del 4% de su facturación global anual (la cifra más alta), por incumplimientos respecto de determinados requisitos del RGPD. Las reclamaciones individuales adicionales pueden incrementar su riesgo si no cumple con los requisitos del RGPD.

**¿Mi empresa debe designar un responsable encargado de la protección de datos (DPO)?**

Depende de diferentes factores recogidos en el reglamento. El artículo 37 del RGPD establece que los controladores y procesadores deberán designar un responsable de protección de datos en cualquiera de estos casos: (a) el procesamiento se lleva a cabo por parte de una autoridad u organismo público, excepto en el caso de tribunales cuando actúen conforme con sus funciones judiciales; (b) las actividades principales del controlador o del procesador consisten en actividades de procesamiento que, debido a su naturaleza, ámbito y/o propósito, requiere una supervisión regular y sistemática de los datos a gran escala; o (c) las actividades principales del controlador o del procesador consisten en el procesamiento a gran escala de los datos indicados en el artículo 9 y datos personales relacionados con condenas penales y delitos indicados en el artículo 10.

**¿Cuánto costará lograr la conformidad con el RGPD?**

La conformidad con el RGPD supondrá costes en términos de dinero y tiempo para la mayoría de organizaciones, si bien puede ser una transición más atenuada para aquellas organizaciones que estén trabajando en un modelo de servicios en la nube con una buena arquitectura y ya hayan implementado un programa eficaz de gobernanza de datos.

**¿Cómo puedo saber si los datos que procesa mi organización están cubiertos por el RGPD?**

El RGPD regula la recopilación, el almacenamiento, el uso y la forma en que se comparten los «datos personales». Los datos personales se definen ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable.

Entre los datos personales se pueden incluir, entre otros, identificadores en línea (por ejemplo, direcciones IP), información de empleados, bases de datos de ventas, datos de servicios de clientes, formularios de comentarios de los clientes, datos de ubicación, datos biométricos, grabaciones de CCTV, registros de programas de fidelización, información sanitaria y financiera, entre otros muchos más. Incluso pueden incluir información que no parezca personal, como una fotografía de un paisaje sin personas, cuando esta información esté vinculada a un número de cuenta o un código único para una persona identificable. Incluso los datos personales registrados bajo seudónimo pueden constituir datos personales si el seudónimo se puede vincular a una persona concreta. 

El procesamiento de determinadas categorías «especiales» de datos personales, como los datos personales que revelan el origen racial o étnico de una persona o relacionados con su salud u orientación sexual, está sujeto a reglas más estrictas que el procesamiento de datos personales «ordinarios». Esta evaluación de datos personales es muy específica, por lo que se recomienda contratar a un experto para evaluar sus circunstancias específicas.

**Mi organización solo procesa datos en nombre de terceros. ¿Debe cumplir igualmente con el RGPD?**

Sí. Aunque las reglas son ligeramente distintas, el RGPD se aplica a las organizaciones que recopilación y procesan datos para sus propios propósitos («controladores») y a las organizaciones que procesan los datos en nombre de terceros («procesadores»). Este requisito es un cambio respecto de la Directiva de protección de datos existente, que se aplica a los controladores.

**¿Qué se considera específicamente datos personales?**

Los datos personales son cualquier información relacionada con una persona identificada o identificable. No hay distinción entre los roles privados, públicos o laborales de una persona. Los datos personales pueden incluir:

- Nombre
- Dirección del domicilio
- Dirección del trabajo
- Número de teléfono
- Número de celular
- Dirección de correo
- Número de pasaporte
- Documento de identificación nacional
- Número de la Seguridad Social (o equivalente)
- Licencia de conducir
- Información física, psicológica o genética
- Información médica
- Identidad cultural
- Información bancaria y números de cuentas
- Número de identificación fiscal
- Dirección de lugar de trabajo
- Números de tarjetas de crédito y débito
- Publicaciones de las redes sociales
- Publicaciones de las redes sociales
- Dirección IP (región de la UE)
- Datos de ubicación y GPS
- Cookies

**¿Puedo transferir datos fuera de la UE?**

Sí, si bien el RGPD regula estrictamente las transferencias de datos de residentes europeos a destinos situados fuera del Espacio Económico Europeo. Puede que deba configurar un mecanismo legal específico, como un contrato, o someterse a determinados mecanismos a fin de habilitar estas transferencias. Microsoft detalla los mecanismos que utilizamos en los términos de los servicios en línea.

**Tengo requisitos de conservación de datos en virtud de la conformidad. ¿Estos requisitos se superponen al derecho de eliminación?**

En caso de que existan fundamentos legítimos para el procesamiento continuado y la retención de los datos, como en caso de «cumplimiento con una obligación legal que requiere el procesamiento en virtud de una ley de la Unión o de un Estado miembro a la que el controlador está sometido» (artículo 17(3)(b)), el RGPD reconoce la posibilidad de que las organizaciones estén obligadas a conservar datos. En todo caso, deberá contar la participación de sus servicios de asesoría legal para asegurarse de que los fundamentos para la conservación son compatibles con los derechos y libertades de los interesados, sus expectativas en el momento en que los datos fueron recopilados, etc.

**¿Es compatible el RGPD con el cifrado?**

El cifrado se identifica en el RGPD como medida de protección que hace los datos ininteligibles cuando se ven afectados por una infracción. Por lo tanto, tanto si se usa como si no, el cifrado puede afectar a los requisitos de notificación de infracción de datos personales. El RGPD también señala el cifrado como medida técnica u organizativa apropiada en determinados casos, en función del riesgo. El cifrado es también un requisito en el Estándar de Seguridad de Datos del Sector de Tarjetas de Pago y está incluido en las estrictas directivas de cumplimiento específicas para el sector de servicios financieros. Los productos y servicios de Microsoft, como Azure, Dynamics 365, Enterprise Mobility + Security, Office Microsoft 365, SQL Server/Azure SQL Database y Windows 10 proporcionan un potente cifrado para datos en tránsito y estacionarios.

**¿Cómo cambia el RGPD la respuesta de las organizaciones frente a infracciones de datos personales?**

El RGPD cambiará los requisitos de protección de datos e impondrá obligaciones más estrictas a los procesadores y controladores en cuanto a la notificación de infracciones de datos personales. De conformidad con el nuevo reglamento, el procesador debe notificar al controlador de los datos sobre la violación de datos personales una vez tenga conocimiento de ello y sin demoras indebidas. Una vez que tenga conocimiento de la infracción de los datos personales, el controlador debe notificar a la autoridad de protección de datos correspondiente dentro de 72 horas. Si es probable que la infracción suponga un alto riesgo para los derechos y libertades de las personas, el controlador también deberá notificar a las personas afectadas sin demoras indebidas. El grupo de trabajo del artículo 29 de la UE está desarrollando orientación adicional en relación con esta materia.

Los productos y servicios de Microsoft (como Azure, Dynamics 365, Enterprise Mobility + Security, Microsoft Office 365 y Windows 10) disponen de soluciones disponibles para ayudarle a detectar y evaluar las amenazas a la seguridad y las infracciones, así como a cumplir con las obligaciones de notificación del RGPD.

## <a name="additional-resources"></a>Recursos adicionales

- [Aborde sus necesidades en relación con el RGPD con uno de nuestros socios globales que ofrecen soluciones basadas en Microsoft](https://aka.ms/findgdprpartner)
- [Obtenga información acerca de cómo administra Microsoft sus datos, dónde están ubicados, quién puede acceder a ellos y mucho más.](https://www.microsoft.com/trust-center/privacy)
- [Obtenga más información sobre cómo Microsoft cumple con los principios del marco Privacy Shield entre la UE y EE. UU.](https://blogs.microsoft.com/eupolicy/2016/07/11/eu-u-s-privacy-shield-progress-for-privacy-rights/)
- [Cómo detecta y responde Microsoft a una vulneración de datos personales y se la comunica a usted en virtud del RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-data-breach)
- [Evalúe hoy mismo su nivel de preparación ante el RGPD](https://discover.microsoft.com/gdpr-readiness-assessment/)
