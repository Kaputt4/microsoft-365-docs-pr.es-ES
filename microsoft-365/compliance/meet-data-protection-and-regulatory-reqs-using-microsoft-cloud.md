---
title: Cumpla con la protección de datos y los requisitos normativos con Administrador de cumplimiento para los servicios en la nube de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 429e686f-d8a6-455e-a2b6-3791d763f000
description: Obtenga información acerca de cómo usar el Administrador de cumplimiento en el Portal de confianza del servicio de Microsoft para satisfacer los requisitos normativos y de protección de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 071da43244f2afae3df29ec84ae98713ed0dc2d7
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815601"
---
# <a name="microsoft-compliance-manager-classic"></a>Administrador de cumplimiento de Microsoft (clásico)

> [!NOTE]
> En esta documentación se describe una versión anterior de este producto. No se aconseja a los usuarios usar esta versión del Administrador de cumplimiento sino que se les aconseja usar la nueva [Puntuación de cumplimiento de Microsoft](compliance-score.md).

 *El Administrador de cumplimiento no está disponible en Office 365 ofrecido por 21Vianet, Office 365 Germany, Office 365 U.S. Government Community High (GCC High) u Office 365 Department of Defense.*
  
El Administrador de cumplimiento, una herramienta de evaluación de riesgos basada en flujo de trabajo en el [Portal de confianza de servicios](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal) de Microsoft, le permite realizar un seguimiento, asignar y verificar las actividades de cumplimiento reglamentario de su organización en relación con los Servicios profesionales de Microsoft y los Servicios en la nube de Microsoft, como Microsoft Office 365, Microsoft Dynamics 365 y Microsoft Azure. 

Administrador de cumplimiento:
  
- Combina la información detallada proporcionada por Microsoft a auditores y entidades reguladoras como parte de distintas auditorías de terceros de los Servicios en la nube de Microsoft en relación con distintas normas (como ISO 27001, ISO 27018 y NIST) e información que Microsoft recopila internamente para su cumplimiento con reglamentos (como HIPAA y el Reglamento general de protección de datos de la UE o RGPD) con su propia autoevaluación del cumplimiento de su organización de estas normas y reglamentos.
    
- Le permite asignar, realizar un seguimiento y registrar actividades relacionadas con evaluaciones y cumplimiento, lo que puede ayudar a su organización a cruzar las barreras de los equipos para alcanzar los objetivos de cumplimiento.
    
- Proporciona una puntuación de cumplimiento para realizar un seguimiento de su progreso y priorizar los controles de auditoría que permitirán reducir la exposición a los riesgos de su organización.
    
- Proporciona un repositorio seguro para que pueda cargar y administrar evidencias y otros artefactos relacionados con sus actividades de cumplimiento.
    
- Proporciona informes detallados enriquecidos en Microsoft Excel donde se documentan las actividades de cumplimiento realizadas por Microsoft y su organización, y que pueden proporcionarse a auditores, entidades reguladoras y otras partes interesadas de cumplimiento.

Para ver una breve demostración del Administrador de cumplimiento, vea el vídeo [Administrador de cumplimiento](https://www.youtube.com/watch?v=r1vs8NdSXKQ).

    
> [!IMPORTANT]
> Compliance Manager is a dashboard that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance. The Customer Actions provided in Compliance Manager are recommendations; it is up to each organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation. Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.

    
## <a name="what-is-compliance-manager"></a>¿Qué es el Administrador de cumplimiento?

Compliance Manager is a workflow-based risk assessment tool designed to help you manage regulatory compliance within the shared responsibility model of the cloud. Compliance Manager provides you with a dashboard view of standards and regulations and assessments that contain Microsoft's control implementation details and test results and customer control implementation guidance and tracking for your organization to enter. Compliance Manager provides certification assessment control definitions, guidance on implementation and testing of controls, risk-weighted scoring of controls, role-based access management, and an in-place control action assignment workflow to track control implementation, testing status and evidence management. Compliance Manager optimizes compliance workload by enabling customers to logically group assessments together and apply assessment control testing to identical or related controls, reducing the duplication of effort that might otherwise be required to satisfy identical control requirements across different certifications.

## <a name="assessments-in-compliance-manager"></a>Evaluaciones en el Administrador de cumplimiento

The core component of Compliance Manager is called an *Assessment*. An Assessment is an assessment of a Microsoft service against a certification standard or data protection regulation (such as ISO 27001:2013, and the GDPR). Assessments help you to discern your organization's data protection and compliance posture against the selected industry standard for the selected Microsoft cloud service. Assessments are completed by the implementation of the controls that map to the certification standard being assessed. 
  
La estructura de una evaluación se basa en la responsabilidad compartida entre Microsoft y su organización para evaluar riesgos de seguridad y cumplimiento en la nube, así como para implementar las medidas de protección de datos especificadas por una norma de cumplimiento, una norma de protección de datos, un reglamento o una ley.
  
Una evaluación está formada por varios componentes:
  
- **Servicios dentro del ámbito**: cada evaluación se aplica a un conjunto específico de servicios Microsoft, que se indican en la sección Servicios en la nube dentro del ámbito. 
    
- **Microsoft-Managed Controls** - For each cloud service, Microsoft implements and manages a set of  *controls*  as part of Microsoft's compliance with various standards and regulations. These controls are organized into  *control families*  that align with the structure from the corresponding certification or regulation that the Assessment is aligned to. For each Microsoft-managed control, Compliance Manager provides details about how Microsoft implemented the control, along with how and when that implementation was tested and validated by an independent third-party auditor. 
    
    Este es un ejemplo de tres controles administrados por Microsoft en la familia de controles **Seguridad** de una evaluación de Office 365 y RGPD. 

    ![Detalles de controles administrados por Microsoft en el Administrador de cumplimiento](../media/d1351212-1ebf-424e-91b8-930c2b2edef1.png)
  
  a. Specifies the following information from the certification or regulation that maps to the Microsoft-managed control.

  - **Id. de control**: el número de artículo o sección de la certificación o reglamento al que se asigna el control.
    
  - **Título**: el título de la certificación o reglamento correspondiente.
    
  - **Id. de artículo**: este campo solo se incluye para evaluaciones del RGPD y especifica el número de artículo del RGPD correspondiente.
    
  - **Descripción**: texto de la norma o reglamento que se asigna al control administrado por Microsoft seleccionado.

  b. The Compliance Score for the control, which indicates the level of risk (due to non-compliance or control failure) associated with each Microsoft-managed control. See [Understanding the Compliance Score](#understanding-the-compliance-score) for more information. Note that Compliance Scores are rated from 1 to 10 and are color-coded. Yellow indicates low risk controls, orange indicates medium-risk controls, and red indicated high-risk controls. 
    
  c. Information about the implementation status of a control, the date the control was tested, who performed the test, and the test result.
    
  d. For each control, you can click **More** to see additional information, including details about Microsoft's implementation of the control and details about how the control was tested and validated by an independent third-party auditor. 
    
- **Customer-Managed Controls** - This is the collection of controls that are managed by your organization. Your organization is responsible for implementing these controls as part of your compliance process for a given standard or regulation. Customer-managed controls are also organized into control families for the corresponding certification or regulation. Use the customer-managed controls to implement the recommended actions suggested by Microsoft as part of your compliance activities. Your organization can use the prescriptive guidance and recommended Customer Actions in each customer-managed control to manage the implementation and assessment process for that control.
    
    Customer-managed controls in Assessments also have built-in workflow management functionality that you can use to manage and track your organization's progress towards completing the Assessment. For example, a Compliance Officer in your organization can assign an Action Item to an IT admin who has the responsibility and necessary permissions to perform the actions that are recommended for the control. When that work is complete, the IT admin can upload evidence of their implementation tasks (for example, screenshots of configuration or policy settings) and then assign the Action Item back to the Compliance Officer to evaluate the collected evidence, test the implementation of the control, and record the implementation date and test results in Compliance Manager. For more information, see the [Managing the assessment process](#managing-the-assessment-process) section in the article. 
  
## <a name="permissions-and-role-based-access-control"></a>Permisos y control de acceso basado en roles

El administrador de cumplimiento utiliza un modelo de permisos de control de acceso basado en roles. Solo los usuarios a los que se les asigne un rol pueden acceder al administrador de cumplimiento, y las acciones permitidas por cada usuario están restringidas según el tipo de rol.
  
Tenga en cuenta que ya no hay un rol predeterminado **acceso de invitado** Se debe asignar un rol a cada usuario para que tenga acceso y trabaje en administrador de cumplimiento
  
The following table describes each Compliance Manager permission and what it allows the user do. The table also indicates the role that each permission is assigned to.
  
||**Lector del Administrador de cumplimiento**|**Colaborador del Administrador de cumplimiento**|**Evaluador del Administrador de cumplimiento**|**Administrador del Administrador de cumplimiento**|**Administrador del portal**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Leer datos**: los usuarios pueden leer datos, pero no pueden editarlos.  <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|
|**Editar datos**: los usuarios pueden editar todos los campos, excepto “Resultado de la prueba” y “Fecha de la prueba”.  <br/> ||![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Editar resultados de pruebas**: los usuarios pueden editar los campos “Resultado de la prueba” y “Fecha de la prueba”.  <br/> ||<br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Administrar evaluaciones**: los usuarios pueden crear, archivar y eliminar evaluaciones.  <br/> |||<br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Manage users** - Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles. Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.  <br/> ||||<br/> |![Marca de verificación](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
## <a name="understanding-the-compliance-score"></a>Información sobre la puntuación de cumplimiento

En el tablero de instrumentos, el Administrador de cumplimiento muestra la puntuación total de las evaluaciones de Office 365 en la esquina superior derecha de la bandeja. Esta es la puntuación total de cumplimiento total de la evaluación, y es la acumulación de puntos recibidos por cada evaluación de control que ha sido calificada como Implementada y Probada en la evaluación. Al agregar una Valoración, verá que la puntuación de cumplimiento ya está activada hasta finalizar, debido a que ya se han aplicado los puntos para los controles administrados por Microsoft que han sido implementados además de ser probados y aplicados por terceros independientes.
  
![Panel del Administrador de cumplimiento: Puntuación de cumplimiento total](../media/756091aa-1afd-4aff-93ab-c6f6824f2add.png)
  
Los puntos restantes provienen de la evaluación correcta de controles de cliente y de la implementación y prueba de los controles administrados por el cliente, cada uno con un valor específico que contribuye a la puntuación de cumplimiento global. 
  
Cada evaluación muestra una puntuación de cumplimiento basada en el riesgo para ayudarle a evaluar el nivel de riesgo (debido a un incumplimiento o fallo de control) asociado con cada control (incluidos los controles administrados por Microsoft y los administrados por el cliente) en una evaluación. Se asigna una cantidad de puntos posibles (denominada clasificación de gravedad) a todos los controles administrados por el cliente, con una escala de 1 a 10, donde se asignan más puntos a los controles asociados a un mayor factor de riesgo si el control produce errores, mientras que se asignan menos puntos a los controles con riesgo bajo. 
  
Por ejemplo, el control de evaluación “Administración de acceso de usuario” que se muestra abajo tiene una clasificación de riesgo de gravedad muy alta y se muestra un valor asignado de 10.
  
![Administrador de cumplimiento: Gravedad alta de control de evaluación (puntuación de 10)](../media/174ecb2c-aaed-436e-9950-74da7dadf5db.png)
  
 En comparación, el control de evaluación “Copia de seguridad de la información” que se muestra abajo tiene una clasificación de riesgo de gravedad inferior y se muestra con un valor asignado de 3. 
  
![Administrador de cumplimiento: Gravedad baja de control de evaluación (puntuación de 3)](../media/11749f20-5f22-40c2-bbc1-eaccbf29e2ae.png)
  
The Compliance Manager assigns a default severity ranking to each control. Risk rankings are calculated based on the following criteria:
  
- Si un control evita que ocurran incidentes (clasificación más alta), detecta los incidentes que han ocurrido o soluciona el impacto de un incidente (clasificación más baja). En términos de clasificación de gravedad, a un control obligatorio que previene una amenaza se le asigna el mayor número de puntos; a los controles que son detectables o correctivos (independientemente de si son obligatorios o discrecionales) se les asigna el menor número de puntos.
    
- Si un control (después de su implementación) es obligatorio y, por lo tanto, los usuarios no pueden omitirlo (por ejemplo, usuarios que tengan que restablecer la contraseña y que esta cumpla con requisitos de caracteres y longitud); o bien si un control es discrecional y los usuarios pueden omitirlo (por ejemplo, reglas empresariales que obligan a los usuarios a bloquear la pantalla cuando dejan el equipo sin supervisión).
    
- Controls related to risks to data confidentiality, integrity, and availability, whether these risks come from internal or external threats, and whether the threat is malicious or accidental. For example, controls that would help prevent an external attacker from breaching that network and gaining access to personally identifiable information would be assigned more points than a control related to preventing an employee from accidentally mis-configuring a network router setting that results in a network outage).
    
- Los riesgos relacionados con factores externos y jurídicos de cada control, como contratos, reglamentos y compromisos públicos.
    
The displayed Compliance Score values for the control are applied  *in their entirety*  to the Total Compliance Score on a pass/fail basis--either the control is implemented and passes the subsequent assessment test or it does not; there is no partial credit for a partial implementation. Only when the control has its **Implementation Status** set to **Implemented** or **Alternative Implementation** and the **Test Result** is set to **Passed** are the assigned points added to the Total Compliance Score. 
  
Lo más importante es que la puntuación de cumplimiento puede ayudarle a identificar los controles que tiene que implementar, porque le indica cuáles tienen un riesgo potencial más alto si se produce un error relacionado con el control. Además de la priorización basada en el riesgo, cuando los controles de la evaluación están relacionados con otros controles (ya sea dentro de la misma evaluación o en otra evaluación dentro de la misma agrupación de evaluaciones), si se completa con éxito un solo control, se puede conseguir una reducción significativa del esfuerzo basado en la sincronización de los resultados de las pruebas de control.
  
Por ejemplo, en la imagen siguiente, la evaluación “Office 365: RGPD” se completó al 46 %, con 51 de 111 evaluaciones de control completadas para una puntuación de cumplimiento total de 289 de un máximo posible de 600.
  
![Administrador de cumplimiento: Resumen de la evaluación](../media/595eedae-e3e0-4d1f-8cf5-7c1c9f4fd1e8.png)
  
Dentro de la evaluación, el control de RGPD 7.5.5 está relacionado con otros 5 controles (7.4.1, 7.4.3, 7.4.4, 7.4.8 y 7.4.9) cada uno con una calificación de riesgo de gravedad moderada a alta de 6 o 8). Usando el filtro de evaluación, se han seleccionado todos estos controles, haciéndolos visibles en la vista de evaluación, y se puede ver a continuación que ninguno de ellos ha sido evaluado. 
  
![Administrador de cumplimiento: Vista de evaluación (controles de filtro, ninguno evaluado)](../media/b2ae7120-2d7a-4247-b0a9-f5f65433395f.jpg) As those 6 controls are related, the completion of any one them will result in a synchronization of those test results across the related controls within this assessment (just as it will for any related controls in an assessment that is in the same assessment grouping). Upon completion of the implementation and testing of GDPR control 7.5.5, the control detail area refreshes to show that all 6 controls have been assessed, with a corresponding increase in the number of assessed controls to 57 and 51% assessed, and a change in total Compliance Score of +40. 
  
![Vista de evaluación del Administrador de cumplimiento: Resultados del control sincronizados](../media/e9da2b30-053a-4d40-ace9-ae1b39cdaf66.jpg)
  
Este cuadro de diálogo de confirmación de la actualización se mostrará si va a cambiar el estado de la implementación de un control relacionado de forma que afecte al resto de los controles relacionados.
  
![Evaluación del Administrador de cumplimiento: Cuadro de diálogo de confirmación de actualización de controles relacionados](../media/8be25bd2-1aee-455f-8aa4-10b1184ca4c3.png)
  
> [!NOTE]
> Currently, only Assessments for Office 365 cloud services include a Compliance Score. Assessments for Azure and Dynamics show an assessment status. 

## <a name="compliance-score-methodology"></a>Metodología de puntuación de cumplimiento

La puntuación de cumplimiento, al igual que Microsoft Secure Score, es similar a otros sistemas de puntuación basada en el comportamiento; la actividad de su organización puede incrementar su puntuación de cumplimiento si realiza actividades relacionadas con la seguridad, privacidad y protección de datos.
  
> [!NOTE]
> The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way. 
  
Assessments in Compliance Manager are based on the shared responsibility model for cloud computing. In the shared responsibility model, Microsoft and each customer share responsibility for the protection of the customer's data when that data is stored in our cloud.
  
Como se muestra en la Evaluación de RGPD de Office 365 a continuación, Microsoft y los clientes son responsables de realizar diferentes acciones que están diseñadas para cumplir los requisitos del reglamento o estándar que se evaluará. Racionalizar y comprender lo que se requiere. Actuando a través de una variedad de estándares y regulaciones, el Administrador de Cumplimiento trata todos los estándares y reglamentos como si fueran marcos de control. Por tanto, las acciones realizadas por Microsoft y por clientes para cada evaluación implican la implementación y la validación de los distintos controles.
  
![Administrador de cumplimiento: Evaluación del RGPD](../media/123f8126-85b8-4baa-9c4e-c6295cf4a5ca.png)
  
Este es el flujo de trabajo básico para una acción típica:
  
1. The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns the task to someone in the organization to implement a control. That person could be:

    - Un propietario de la directiva de la empresa
    
    - Un implementador de TI
    
    - Otra persona de la organización que tenga responsabilidad para realizar la tarea
    
2. That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the control(s) tied to the Action as implemented. Once these tasks are completed, they assign the Action to an Assessor for validation. Assessors can be:
    
    - Evaluadores internos que realicen la validación de controles dentro de una organización.
    
    - Evaluadores externos que examinen, verifiquen y certifiquen el cumplimiento, como las organizaciones independientes de terceros que auditan los servicios en la nube de Microsoft.
    
3. El evaluador valida el control, examina las evidencias y marca los controles como evaluados, además de indicar los resultados de una evaluación (por ejemplo, correcta).
    
Después de evaluar todos los controles asociados con una evaluación, esta se considerará completada.
  
Every Assessment in Compliance Manager comes pre-loaded with information that provides details about the Actions taken by Microsoft to satisfy the requirements of the controls for which Microsoft is responsible. This information includes details about how Microsoft has implemented each control and how and when Microsoft's implementation was assessed and verified by a third-party auditor. For this reason, the Microsoft Managed Controls for each Assessment are marked as Assessed, and the Compliance Score for the Assessment reflects this.
  
Each Assessment includes a total Compliance Score based on the shared responsibility model. Microsoft's implementation and testing of controls for Office 365 contributes a portion of the total possible points associated with a GDPR assessment. As the customer implements and tests each of the customer Actions, the Compliance Score for the Assessment will increase by the value assigned to the control. 
  
 ### <a name="risk-based-scoring-methodology"></a>Metodología de puntuación basada en riesgos
  
Compliance Manager uses a risk-based scoring methodology with a scale from 1-10 that assigns a higher value to controls that represent a higher risk in the event the control fails or is non-compliant. The scoring system used by Compliance Score is based on several key factors, such as:
  
- La esencia del control
    
- El nivel de riesgo del control basado en los tipos de amenazas
    
- Los factores externos del control
    
![Administrador de cumplimiento: Metodología de puntuación de cumplimiento](../media/e48764c4-828e-44b0-8636-fb3c352f2bac.png)
  
 ### <a name="essence-of-the-control"></a>Esencia del control
  
La esencia del control depende de si el control es obligatorio o discrecional, y si es preventivo, de investigación o correctivo.
  
 ### <a name="mandatory-or-discretionary"></a>Obligatorio o discrecional
  
 *Mandatory controls*  are controls that cannot be bypassed either intentionally or accidentally. An example of a common mandatory control is a centrally-managed password policy that sets requirements for password length, complexity, and expiration. Users must comply with these requirements in order to access the system. 
  
 *Discretionary controls*  rely upon users to understand policy and act accordingly. For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user. 
  
 ### <a name="preventative-detective-or-corrective"></a>Preventivo, de investigación o correctivo
  
 *Preventative controls*  are those that prevent specific risks. For example, protecting information at rest using encryption is a preventative control against attacks, breaches, etc. Separation of duties is a preventative control to manage conflict of interest and to guard against fraud. 
  
 *Detective controls*  are those that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred. System access auditing and privileged administrative actions auditing are types of detective monitoring controls; regulatory compliance audits are a type of detective control used to find process issues. 
  
 *Corrective controls*  are those that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible. Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach. 
  
Al evaluar cada control con estos factores, determinamos la esencia del control y le asignamos un valor relativo al riesgo que representa.
  
 **Amenaza**
  
||||
|:-----|:-----|:-----|
||**Obligatorio** <br/> |**Discrecional** <br/> |
|**Preventivo** <br/> |Riesgo alto  <br/> |Riesgo medio  <br/> |
|**Investigación** <br/> |Riesgo medio  <br/> |Riesgo bajo  <br/> |
|**Correctivo** <br/> |Riesgo medio  <br/> |Riesgo bajo  <br/> |
   
Una amenaza hace referencia a cualquier acción que implica un riesgo para el estándar de seguridad básico y aceptado universalmente basado en tres factores: confidencialidad, integridad y disponibilidad:
  
- Confidencialidad significa que solo las partes autorizadas y de confianza pueden leer y comprender la información.
    
- Integridad quiere decir que partes no autorizadas no modificaron ni destruyeron la información.
    
- Disponibilidad quiere decir que puede obtener acceso a la información fácilmente con un nivel elevado de calidad de servicio.
    
A failure of any of these characteristics is considered a compromise of the system as a whole. Threats can come from both internal and external sources, and an actor's intent can be accidental or malicious. These factors are estimated in a threat matrix that assigns threat levels of either High, Moderate, or Low to each combination of scenarios.

||**Interna**<br/>||**Externa**<br/>||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||*Malintencionada*<br/>|*Accidental*<br/>|*Malintencionada*<br/>|*Accidental*<br/>|||
|**Confidencialidad**<br/>|(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)|
|**Integridad**<br/>|(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)|
|**Disponibilidad**<br/>|(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)|
   
 **Factores externos**
  
|**Contratos**|**Reglamentos**|**Compromisos públicos**|
|:-----|:-----|:-----|
|(A, M o B)  <br/> |(A, M o B)  <br/> |(A, M o B)  <br/> |
   
Los factores externos (como los compromisos públicos, contratos y reglamentos vigentes) pueden afectar a los controles diseñados para proteger los datos e impedir infracciones de datos, y se asignan valores de riesgo alto, moderado o bajo a cada uno de estos factores.
  
El número estimado de repeticiones de estos valores de riesgo de alto, moderado o bajo en los 15 posibles escenarios de riesgos representados en la matriz de Estándar de seguridad/Amenaza y jurídico/factores externos se combinan para proporcionar una ponderación de riesgos, que tiene en cuenta la probabilidad y el número de repeticiones de riesgos con un valor asignado como importante, y se consideran al calcular la clasificación de gravedad del control.
  
Basándose en la clasificación de gravedad del control, se asignará un valor de puntuación de cumplimiento entre 1 (bajo) y 10 (alto), agrupados en las siguientes categorías de riesgos:
  
|**Nivel de riesgo**|**Valor del control**|
|:-----|:-----|
|Bajo  <br/> |1-3  <br/> |
|Moderado  <br/> |6  <br/> |
|Alto  <br/> |8  <br/> |
|Grave  <br/> |10  <br/> |
   
Al dar prioridad a los controles de evaluación con los valores de puntuación de cumplimiento más elevados, la organización se centrará en los elementos de mayor riesgo y recibirá una respuesta más positiva proporcionalmente, ya que se agregarán más puntos a la puntuación de cumplimiento total por la evaluación completada de cada control.
  
### <a name="summary-of-scoring-methodology"></a>Resumen de la metodología de puntuación
  
The Compliance Score is a core component of the way that Compliance Manager helps organizations understand and manage their compliance. The Compliance Score for an assessment is an expression of the company's compliance with a given standard or regulation as a number, where the higher the score (up to the maximum number of points allocated for the Assessment), the better the company's compliance posture. Understanding the compliance scoring methodology in which assessment controls are assigned risk severity values between 1- 10 (low to high), and how completed control assessments add to the total compliance score is crucial to organizations for prioritizing their actions.

## <a name="grouping-assessments"></a>Agrupación de evaluaciones

Al crear una evaluación, se le pide que cree un grupo al que asignarla o que la asigne a un grupo existente. Los grupos le permiten organizar lógicamente las evaluaciones, así como compartir información común y tareas de flujo de trabajo entre las evaluaciones que tienen los mismos controles administrados por cliente (o relacionados).
  
For example, you could group Assessments by year or teams, departments, or agencies within your organization or group them by year. Here are some examples of groups and the Assessments they might contain.
  
- Evaluaciones del RGPD: 2018
    
  - Office 365 + RGPD
    
  - Azure + RGPD
    
  - Dynamics + RGPD
    
- Evaluaciones de Azure: 2018
    
  - Azure + RGPD
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
- Evaluaciones de privacidad y seguridad de los datos
    
  - Office 365 + ISO 27001:2013
    
  - Office 365 + ISO 27018:2014
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
> [!TIP]
> Le recomendamos que determine una estrategia de agrupación para su organización antes de agregar nuevas evaluaciones. 
  
Estos son los requisitos para agrupar evaluaciones:
  
- Los nombres de grupo (también denominados *id. de grupo) tienen que ser únicos en la organización. 
    
- Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair. For example, a group can't contain two Assessments for Office 365 and GDPR. Similarly, a group can contain multiple Assessments for the same cloud service as long as the corresponding certification/regulation for each one is different.
    
Después de agregar una evaluación a una agrupación de evaluaciones, la agrupación no se puede modificar. Puede cambiar el nombre del grupo de evaluaciones, lo que cambiará el nombre de la agrupación de evaluaciones de todas las evaluaciones asociadas con ese grupo. Puede crear una evaluación y un grupo de evaluaciones, y copiar la información de una evaluación existente, lo que creará un duplicado de esa evaluación y otro grupo de evaluaciones. El archivado de una evaluación rompe la relación entre dicha evaluación y el grupo de evaluación. Cualquier otra actualización de evaluaciones relacionadas no se verá reflejada en la evaluación archivada.
  
Como se ha explicado anteriormente, una de las ventajas más importantes de los grupos se hace patente cuando dos evaluaciones diferentes del mismo grupo comparten un control administrado por el cliente (y, por lo tanto, las acciones de cliente son las mismas para cada control). Así, la cumplimentación de los detalles de la implementación, la información de pruebas y el estado del control en una evaluación se sincroniza con el mismo control de cualquier otra evaluación del grupo. Es decir, si las evaluaciones comparten un control y están en el mismo grupo, solo tendrá que administrar el proceso de evaluación de un control. Los resultados de ese control se sincronizarán automáticamente con otras evaluaciones. Por ejemplo, ISO 27001 e ISO 27018 tienen un control relacionado con las directivas de contraseñas. Si el Estado de la prueba del control es "Correcto" o "Superado" en una evaluación, el control se actualiza (y se marca como "Correcto" o "Superado") en la otra, siempre que ambas evaluaciones formen parte del mismo grupo de evaluaciones.
  
Tomemos como ejemplo estos dos controles de evaluación relacionados, cada uno vinculado con el cifrado de datos en redes públicas, el control 6.10.1.2 en la evaluación del RGPD de Office 365, y el control SC-13 en la evaluación Office 365 - NIST 800-53. Estos son controles de evaluación relacionados, en dos evaluaciones distintas, ambas en el grupo predeterminado. Inicialmente, ninguna evaluación completa evaluaciones de control de cliente, ya que estas dos evaluaciones se muestran en el Panel del Administrador de cumplimiento.
  
![Panel del Administrador de cumplimiento: Evaluaciones agrupadas (antes)](../media/dc0126a3-415c-4fbe-a020-1806dd1caebd.png)
  
Al hacer clic en la evaluación **Office 365: RGPD** y usar los controles de filtro para ver el control del RGPD 6.10.1.2, vemos que el control SC-13 de NIST 800-53 se muestra como un control relacionado.
  
![Evaluación del Administrador de Cumplimiento: Controles compartidos](../media/aafb106e-0abc-4918-8038-de11cf326dfe.png)
  
 Aquí se muestra la finalización de la implementación y pruebas del control del RGPD 6.10.1.2. 
  
![Control de evaluación del Administrador de cumplimiento del RGPD 6.10.1.2: Estado correcto](../media/ee9e83b6-9d51-4b3b-85eb-96bec0fef2e1.png)
  
Al navegar al control relacionado en la evaluación agrupada, vemos que el SC-13 de NIST 800-53 también se marcó como completado con la misma fecha y hora, sin ningún esfuerzo de pruebas o implementación.
  
![Evaluación del Administrador de Cumplimiento: NIST 800-53 SC(13) completado](../media/b5933592-db5a-4fdd-9be2-bba777646a88.png)
  
De nuevo en el panel, podemos ver que cada evaluación tiene una evaluación de control completada y que la puntuación de cumplimiento total de cada evaluación se incrementó en ocho (el valor de la puntuación de cumplimiento del control compartido).
  
![Panel del Administrador de cumplimiento — sincronización del progreso de evaluación agrupada](../media/727f1203-b98d-4a03-a7af-e9236f4c5534.png)

## <a name="administrative-functions"></a>Funciones administrativas

Hay funciones administrativas específicas que solo están disponibles en la cuenta de administrador del espacio empresarial y solo serán visibles al iniciar sesión como administrador global.
  
> [!NOTE]
> The Access to Restricted Documents permission in the drop-down list will allow administrators to give users access to restricted documents that Microsoft shares on the Service Trust Portal. The Restricted Documents feature isn't available, but is coming soon. 
  
### <a name="assigning-compliance-manager-roles-to-users"></a>Asignar roles del Administrador de cumplimiento a usuarios

Each Compliance Manager role has slightly different permissions. You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal by selecting the **Admin** menu item, and then choosing **Settings**. 
  
![Menú Administrador de STP: Configuración seleccionada](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
Para agregar o quitar usuarios de los roles del Administrador de cumplimiento.
  
1. Vaya a [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).
    
2. Inicie sesión con su cuenta de administrador global de Azure Active Directory.
    
3. En la barra de menús superior del Portal de confianza de servicios, haga clic en **Administrador** y, después, seleccione **Configuración**. 
    
4. En la lista desplegable **Seleccionar rol**, haga clic en el rol que quiera administrar. 
    
5. Los usuarios agregados a cada rol se muestran en la página **Seleccionar rol**. 
    
6. To add users to this role, click **Add**. In the **Add Users** dialog, click the user field. You can scroll through the list of available users or begin typing the user name to filter the list based on your search term. Click the user to add that account to the **Add Users** list to be provisioned with that role. If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then click the user to add to the list. Click **Save** to provision the selected role to these users. 
    
    ![Administrador de cumplimiento: Aprovisionar roles (agregar usuarios)](../media/2f386f82-2bf8-4e95-ab41-1724b752b508.png)
  
7. Para quitar usuarios de este rol, seleccione los usuarios y, después, haga clic en **Eliminar**. 
    
    ![Administrador de cumplimiento: Aprovisionar roles (quitar usuario)](../media/17004def-604f-471d-a54d-f678fcc01c1e.png)
 
## <a name="user-privacy-settings"></a>Configuración de privacidad del usuario

Certain regulations require that an organization must be able to delete user history data. To enable this, Compliance Manager provides the **User Privacy Settings** functions, that allow administrators to: 
  
- [Buscar un usuario](#search-for-a-user)

- [Exportar un informe de historial de datos de cuenta](#export-a-report-of-account-data-history)

- [Reasignar acciones](#reassign-action-items)

- [Eliminar el historial de datos de usuarios](#delete-user-data-history)
    
![Administración del Administrador de cumplimiento: Funciones de configuración de privacidad del usuario](../media/067d6c6a-712a-4dc2-9b99-de2fa4417dc3.png)
  
### <a name="search-for-a-user"></a>Buscar un usuario

Para buscar una cuenta de usuario:
  
1. Especifique la dirección de correo electrónico del usuario escribiendo el alias (la información a la izquierda del símbolo @) y elija el nombre de dominio haciendo clic en la lista de sufijos de dominios a la derecha. Si este es un espacio empresarial con varios dominios registrados, puede volver a comprobar el sufijo de nombre de dominio de dirección de correo electrónico para asegurarse de que es correcto.
    
2. Después de especificar correctamente el nombre de usuario, haga clic en **Buscar**. 
    
3. If the user account is not found, the error message 'User not found' will be displayed on the page. Check the user's email address information, make corrections as necessary and click **Search** to try again. 
    
4. Si se encuentra la cuenta de usuario, el texto del botón cambiará de **Buscar** a **Borrar**, lo que indica que la cuenta de usuario encontrada es el contexto operativo para las funciones adicionales que se muestran debajo y que, al ejecutar esas funciones, se aplicarán en la cuenta de usuario. 
    
5. Para borrar los resultados de la búsqueda y buscar otro usuario, haga clic en **Borrar**. 
    
### <a name="export-a-report-of-account-data-history"></a>Exportar un informe de historial de datos de cuenta

Una vez que se haya identificado la cuenta de usuario, puede que desee generar un informe de las dependencias que se encuentran vinculadas a esta cuenta. Esta información le permitirá reasignar los elementos de acción abiertos o garantizar el acceso a evidencias cargadas anteriormente. 
  
 Para generar y exportar un informe:
  
1. Haga clic en **Exportar** para generar y descargar un informe de los elementos de acción de control de Administrador de cumplimiento asignados a la cuenta de usuario devuelta, así como la lista de documentos que ha cargado el usuario. Si no hay acciones asignadas ni documentos cargados, un mensaje de error indicará "No hay datos para este usuario". 
    
2. El informe se descargará en segundo plano desde la ventana del explorador activa (si no ve un mensaje emergente de descarga, consulte el historial de descargas del explorador).
    
3. Abra el documento para revisar los datos del informe.
    
> [!NOTE]
> This is not a historical report that retains and displays state changes to action item assignment history. The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report). For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user. 
  
### <a name="reassign-action-items"></a>Reasignar acciones

This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below. This action does not change document upload history for the returned user account. 
  
 Para reasignar acciones a otro usuario:
  
1. Haga clic en el cuadro de entrada para buscar y seleccionar otro usuario de la organización a quien quiera asignar las acciones del usuario encontrado.
    
2. Seleccione **Reemplazar** para reasignar todas las acciones de control del usuario encontrado al nuevo usuario seleccionado. 
    
3. Aparecerá un cuadro de diálogo de confirmación que indica: "Esto reasignará todos los elementos de acción de control del usuario actual al usuario seleccionado. No se puede deshacer esta acción. ¿Realmente desea continuar?"
    
4. Para continuar, haga clic en **Aceptar**; de lo contrario, haga clic en **Cancelar**. 
    
> [!NOTE]
> All action items (both active and completed) will be assigned to the newly selected user. However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user. 
  
Changing the document upload history to remove the previously assigned user will have to be done as a manual process. In that case, the administrator will need to:
  
1. Abrir el informe exportado que se descargó anteriormente.
  
2. Identificar la acción de control deseada y buscar su ubicación.
  
3. Hacer clic en **Administrar documentos** para abrir el repositorio de evidencias de ese control. 
  
4. Descargar el documento.
  
5. Eliminar el documento del repositorio de evidencias.
  
6. Re-upload the document. The document will now have a new upload date, time and Uploaded By username. 
  
### <a name="delete-user-data-history"></a>Eliminar el historial de datos de usuarios

This sets control action items to 'unassigned' for all action items assigned to the returned user. This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user
  
 Para eliminar el historial de carga de documentos y acciones de la cuenta de usuario:
  
1. Haga clic en **Eliminar**. 

    A confirmation dialog will be displayed, stating "This will remove all control action item assignments and the document upload history for the selected user. This action cannot be undone. Are you sure you want to continue?"
    
3. Para continuar, haga clic en **Aceptar**; de lo contrario, haga clic en **Cancelar**. 
  
## <a name="using-compliance-manager"></a>Uso del Administrador de cumplimiento

El Administrador de cumplimiento proporciona herramientas para asignar, realizar un seguimiento y registrar actividades relacionadas con evaluaciones y cumplimiento, lo que puede ayudar a su organización a cruzar las barreras de los equipos para alcanzar los objetivos de cumplimiento.
  
![Panel del Administrador de cumplimiento: Menú superior (menú Administrador actualizado)](../media/134d7577-cd70-4124-bcfd-d3feb248952b.png)

## <a name="accessing-compliance-manager"></a>Obtener acceso al Administrador de cumplimiento

You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.
  
![Administrador de cumplimiento: Obtener acceso al Administrador de cumplimiento desde el menú de STP](../media/14be4cac-2380-49bc-9b36-210da8cafdfa.png)
  
1. Vaya a [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).
    
2. Inicie sesión con su cuenta de usuario de Azure Active Directory (Azure AD).
    
3. En el Portal de confianza de servicios, haga clic en **Administrador de cumplimiento**. 
    
4. When the Non-Disclosure Agreement is displayed, read it, and then click **Agree** to continue. You'll only have to do this once, and then the Compliance Manager dashboard is displayed. 

    Para ayudarle a empezar, agregamos las siguientes evaluaciones de forma predeterminada:
    
    ![Evaluaciones predeterminadas del Administrador de cumplimiento](../media/8c59b45a-706a-4362-a7ba-2cb782931bf7.png)
    
5. Haga clic en el ![icono de ayuda del Administrador de cumplimiento](../media/c1b3092f-6ac7-43ab-b1c4-63a54598450c.png) **Ayuda** para realizar un paseo breve por el Administrador de cumplimiento. 
  
## <a name="viewing-action-items"></a>Ver acciones

El Administrador de cumplimiento proporciona una vista útil de todas las acciones de evaluaciones de control asignadas, lo que le permite realizar acciones en estas de forma rápida y sencilla. Para ver todas las acciones o seleccionar las acciones que se correspondan con una certificación específica, haga clic en la pestaña asociada con esa evaluación. Por ejemplo, en la imagen siguiente, se seleccionó la pestaña RGPD, donde se muestran controles relacionados con la evaluación del RGPD.
  
![Administrador de cumplimiento: Acciones donde se muestran varias pestañas (RGPD seleccionada)](../media/ba960f5c-becb-4d95-a000-d08ec77b7b46.png)
  
Para ver las acciones:
  
1. Vaya al panel del Administrador de cumplimiento.
    
2. Haga clic en el vínculo **Acciones**; la página se actualizará y se mostrarán las acciones asignadas a su usuario. 
    
    By default, all action items are shown. If you have action items across multiple certifications, the names of the certifications will be listed in tabs across the top of the assessment control. To see the action items for a specific certification, click that tab.

## <a name="adding-an-assessment"></a>Agregar una evaluación

Para agregar una evaluación al Administrador de cumplimiento:
  
1. En el panel del Administrador de cumplimiento, haga clic en ![icono de agregar](../media/ITPro-EAC-AddIcon.gif) **Agregar evaluación**. 
    
2. In the **Add an Assessment** window, you can create a new group to add the Assessment to or you can add it to an existing group (the built-in group is named "Initial Group".) Depending on the option you choose, either type the name of a new group or select an existing group from the drop-down list. For more information, see [Grouping Assessments](#grouping-assessments).
    
    Si crea un grupo, también tendrá la opción de copiar la información de otro existente para la nueva evaluación. Esto significa que la información que se agregó en los campos Detalles de la implementación, Plan de pruebas y Respuesta de la administración de los controles administrados por el cliente de evaluaciones del grupo del que está copiando se pegan en los mismos controles administrados por el cliente (o los relacionados) en la nueva evaluación. Si agrega una evaluación nueva a un grupo existente, la información común de las evaluaciones de ese grupo se copiará a la nueva. Para obtener más información, vea [Copiar la información de evaluaciones existentes](#copying-information-from-existing-assessments).
    
3. Haga clic en **Siguiente** y siga este procedimiento:
    
    a. Elija un servicio en la nube de Microsoft de la lista desplegable **Seleccionar un producto** para evaluar el cumplimiento. 
    
    b. Elija una certificación para evaluar el servicio en la nube seleccionado en la lista desplegable **Seleccionar una certificación**. 
    
4. Haga clic en **Agregar al panel** para crear la evaluación; la evaluación se agregará al panel del Administrador de cumplimiento como un nuevo icono al final de la lista de iconos existentes. 
    
    En el **icono de evaluación** del panel del Administrador de cumplimiento, se muestra la agrupación de evaluaciones, el nombre de la evaluación (creado automáticamente como una combinación del nombre del servicio y la certificación seleccionada), la fecha en que se creó y cuándo se modificó por última vez, la puntuación de cumplimiento total (que es la suma de todos los valores de riesgo de control asignados que se implementaron, probaron y completaron correctamente) e indicadores de progreso en la parte inferior que indican el número de controles evaluados. 
    
5. Haga clic en el nombre de la evaluación para abrirla y vea los detalles de la evaluación.
    
6. Haga clic en el menú **Acciones** para ver las acciones asignadas, cambiar el nombre del grupo de evaluaciones, exportar el informe de evaluación o archivar la evaluación. 
    
    ![Administrador de cumplimiento: Icono de evaluación](../media/abf35c11-9757-45c1-aa14-91178f67a18c.png)

## <a name="copying-information-from-existing-assessments"></a>Copiar información de evaluaciones existentes

Como se ha explicado anteriormente, al crear un grupo de evaluación, tiene la opción de copiar la información de las evaluaciones de un grupo existente a la nueva evaluación en el grupo nuevo. De esta manera, puede aplicar el trabajo de pruebas y evaluación realizado a los mismos controles administrados por el cliente en la nueva evaluación. Por ejemplo, si tiene un grupo para todas las evaluaciones relacionadas con el RGPD en su organización, puede copiar la información común de tareas de evaluación existentes al agregar una nueva evaluación al grupo.
  
Puede copiar la siguiente información del cliente en una nueva evaluación:
  
- Assessment Users. An Assessment user is a user who the control is assigned to.
    
- Estado, fecha de la prueba y resultados de pruebas.
    
- Detalles de la implementación e información sobre el plan de pruebas.
    
Asimismo, se sincroniza la información de controles administrados por el cliente compartidos en el mismo grupo de evaluación. También se sincroniza la información de controles administrados por el cliente relacionados en la misma evaluación.

## <a name="viewing-assessments"></a>Ver evaluaciones

1. Busque el icono de evaluación que se corresponda con la evaluación que quiera ver y, después, haga clic en el nombre de la evaluación para abrirla y ver controles administrados por el cliente y por Microsoft asociados a la evaluación, además de una lista de los servicios en la nube que están dentro del ámbito de la evaluación. Este es un ejemplo de la evaluación para Office 365 y el RGPD.
    
    ![Vista de evaluación del Administrador de cumplimiento: Pantalla completa con globos](../media/169a02eb-e805-412d-b9e7-89561aa7ad1d.png)
  
1. En esta sección, se muestra información de resumen de la evaluación, como el nombre de la agrupación de evaluaciones, el producto, el nombre de la evaluación y el número de controles de evaluación.
    
2. This section shows the Assessment Filter controls. For a more detailed explanation of how to use the Assessment Filter controls see the [Managing the assessment process](#managing-the-assessment-process) section. 
    
3. En esta sección, se muestran los servicios en la nube individuales que están dentro del ámbito de la evaluación.
    
4. Esta sección contiene los controles administrados por Microsoft. Los controles relacionados se organizan en familias. Haga clic en una familia para expandirla y mostrar los controles individuales.
    
5. Esta sección contiene los controles administrados por el cliente, que también se organizan en familias. Haga clic en una familia para expandirla y mostrar los controles individuales.
    
6. Muestra el número total de controles de la familia y cuántos de ellos se han evaluado. Una función principal del Administrador de cumplimiento es seguir el progreso de su organización en la evaluación de los controles administrados por el cliente. Para obtener más información, vea la sección [Introducción a la Puntuación de cumplimiento](#understanding-the-compliance-score). 

## <a name="managing-the-assessment-process"></a>Administrar el proceso de evaluación

Inicialmente, el creador de una evaluación es su único usuario. Para cada control administrado por el cliente, puede asignar un elemento de acción a una persona de su organización. De esta manera, dicha persona se convierte en un usuario de evaluación que puede realizar las acciones de cliente recomendadas, así como recopilar y cargar las pruebas. Al asignar un elemento de acción, puede enviar un correo electrónico a esa persona con información sobre las acciones de cliente recomendadas y la prioridad del elemento de acción. La notificación por correo electrónico incluye un vínculo al panel **Elementos de acción**, en el que se enumeran todos los elementos de acción asignados a ese usuario. 
  
Esta es una lista de las tareas que puede realizar con las características de flujo de trabajo del Administrador de cumplimiento.
  
![Flujo de trabajo de evaluación del Administrador de cumplimiento con globos](../media/9e5ae34d-b55e-4452-a021-e0e5b10218f5.png)
  
1. **Usar las opciones de filtro para encontrar controles de evaluación específicos**: el Administrador de cumplimiento proporciona **opciones de filtro**, que ofrecen criterios de selección altamente granulares para mostrar controles de evaluación, lo que le permitirá dedicarse de forma precisa a áreas específicas de sus esfuerzos de cumplimiento. 
    
    Haga clic en el icono de embudo de la parte derecha de la página para mostrar u ocultar los controles de **Opciones de filtro**. Estos controles le permiten especificar criterios de filtro, y en la parte inferior solo se mostrarán los controles de evaluación que se correspondan con esos criterios. ![Controles de filtro de evaluaciones del Administrador de cumplimiento](../media/d44e1b4b-d928-4778-8a3a-6231edde9ca0.png)
  
    - **Artículos**: filtra el nombre del artículo y devuelve los controles de evaluación asociados con ese artículo. Por ejemplo, al escribir “Artículo (5)”, se muestra una lista de selección de artículos cuyo nombre contiene esa cadena (es decir, artículo (5)(1)(a), artículo (5)(1)(b), artículo (5)(1)(c), etc.). Si selecciona el artículo (5)(1)(c) se le mostrarán solo los controles asociados con dicho artículo. Este es un campo de selección múltiple que usa un operador “O” con varios valores (por ejemplo, si selecciona el artículo (5)(1)(a) y, después, agrega el artículo (5)(1)(c), el filtro mostrará los controles asociados con el artículo (5)(1)(a) o con el artículo (5)(1)(c)). 
    
      ![Vista de evaluación del Administrador de cumplimiento: Filtrar por nombre de artículo](../media/8b0507a0-589d-484a-bc60-80a3debe3ddb.png)
  
    - **Controles**: muestra la lista de controles cuyos nombres coinciden con el filtro (por ejemplo, al escribir 7.3, se mostrará una lista de selección de elementos como, 7.3.1, 7.3.4, 7.3.5, etc.). Es un campo de selección múltiple que usa un operador OR con varios valores (por ejemplo, si selecciona 7.3.1 y, después, agrega 7.3.4, el filtro mostrará los controles asociados con 7.3.1 o 7.3.4). 
    
      ![Vista de evaluación del Administrador de cumplimiento: Selección múltiple de controles de filtro](../media/c4fc25e8-2376-4f2d-b605-f9c3d90413bf.png)
  
    - **Usuarios asignados**: muestra la lista de controles asignados al usuario seleccionado. 
    
    - **Estado**: muestra la lista de controles con el estado seleccionado. 
    
    - **Resultado de la prueba**: muestra la lista de controles con el resultado de la prueba seleccionada. 
    
    As you apply filter conditions, the view of applicable controls will change to correspond to your filter conditions. Expand the control family sections to show the control details below. 
    
    ![Vista de evaluación del Administrador de cumplimiento: Filtrar resultados de artículos](../media/e6485d45-d47f-4b25-8b1c-b3c2ee4a8328.png)
  
2. If after selecting the desired filters no results are shown, that means there are no controls that correspond to the specified filter conditions. For instance, if you select a particular **Assigned User** and then choose a **Control** name that does correspond to the control assigned to that user, no assessments will be shown in the page below. 
    
3. **Assign an Action Item to a user** - You can assign an Action Item to a person to implement the requirements of a certification/regulation, or to test, verify, and document your organization's implementation requirements. When you assign an Action Item, you can choose to send an email to the person that contains details including the recommended Customer Actions and the Action Item priority. You can also unassign or reassign an Action Item to a different person. 
    
4. **Administrar documentos** Los controles administrados por el cliente también cuentan con una ubicación para administrar documentos relacionados con la realización de tareas de implementación, así como para realizar tareas de validación y pruebas. Cualquier persona que tenga permisos para editar datos en el Administrador de cumplimiento puede cargar documentos haciendo clic en **Administrar documentos**. Cuando se hayan cargado documentos, podrá hacer clic en **Administrar documentos** para ver y descargar los archivos. 
    
5. **Proporcionar detalles de pruebas de implementación**: todos los controles administrados por el cliente tienen un campo editable donde los usuarios pueden agregar detalles de la implementación para documentar los pasos realizados por la organización para cumplir con los requisitos de la certificación o reglamento, así como para validar y documentar la forma en que la organización cumple esos requisitos.
    
6. **Set Status** - Set the Status for each item as part of the assessment process. Available status values are **Implemented**, **Alternative Implementation**, **Planned**, and **Not in Scope**. 
    
7. **Escribir la fecha y el resultado de la prueba** La persona con el rol Evaluador de Administrador de cumplimiento puede comprobar que se realizan las pruebas adecuadas, así como revisar los detalles de la implementación, el plan de pruebas, los resultados de las pruebas y cualquier evidencia cargada y, después, establecer los valores de Fecha de la prueba y Resultado de la prueba. Los valores disponibles para Resultado de la prueba son **Correcto**, **Erróneo - Riesgo bajo**, **Erróneo - Riesgo medio** y **Erróneo - Riesgo alto**. 

## <a name="managing-action-items"></a>Administrar acciones

Las personas involucradas en el proceso de evaluación de la organización pueden usar el Administrador de cumplimiento para revisar los controles administrados por el cliente de todas las evaluaciones en las que son usuarios. Cuando un usuario inicia sesión en Administrador de cumplimiento y abre el panel **Elementos de acción**, ve una lista de los que tiene asignados. Según el rol de Administrador de cumplimiento asignado al usuario, este podrá proporcionar detalles sobre la prueba o la implementación, actualizar el estado o asignar elementos de acción. 
  
As certification controls are generally implemented by one person and tested by another, the control action item can be initially assigned to one person for implementation, and once that is complete, that person can reassign the control action item to the next person for control testing and uploading of evidence. This assignment/reassignment of control actions can be performed by any users who have a Compliance Manager role with sufficient permissions, allowing for central management of control assignments, or decentralized routing of control action items, from implementer to tester as appropriate.
  
Para asignar una acción:
  
1. En el panel del Administrador de cumplimiento, busque el icono de evaluación junto a la evaluación con la que quiera trabajar y, después, haga clic en el nombre para ir a la página de detalles.
    
2. Puede hacer clic en **Filtrar** y usar los controles de filtro para encontrar el control de evaluación específico que quiera asignar. 
    
3. También puede ir a la sección Controles administrados por el cliente, expandir la familia de controles y desplazarse por la lista de controles hasta que encuentre el control de evaluación que quiera asignar.
    
4. En la columna **Usuario asignado**, haga clic en **Asignar**. 
    
5. In the Assign Action Item dialog box, click the **Assign To** field to populate the list of users to whom the action can be assigned. You can scroll through the list to find the target user or start typing in the field to search for the username. 
    
6. Haga clic en un usuario para asignarle esta acción.
    
7. Para enviar una notificación por correo electrónico al usuario, asegúrese de que esté activada la casilla **Enviar notificación por correo electrónico**. 
    
8. Escriba las notas que quiera que se muestren al usuario y haga clic en **Asignar**. 
 
    El usuario recibirá una notificación de la asignación de acción, así como las notas que especifique.
    
The notes that are associated with the action item are persisted in the notes section, available for the next time the action item is assigned. These notes are not read-only, can be edited, replaced or removed by the person assigning the action item.

## <a name="exporting-information-from-an-assessment"></a>Exportar información de una evaluación

Puede exportar una evaluación a un archivo de Excel para que las partes interesadas de cumplimiento lo revisen, o bien para facilitarlo a auditores y organismos reguladores. Este informe de evaluación es una instantánea de la evaluación en la fecha y hora en que se creó el informe, y contiene los detalles de los controles administrados por Microsoft y por el cliente para esa evaluación, incluido el estado de la implementación de controles, la fecha de pruebas de control y los resultados de pruebas, y proporciona vínculos a los documentos de evidencias cargados. Le recomendamos que exporte el informe de evaluación antes de archivar una evaluación, ya que en las evaluaciones archivadas no se conservan los vínculos a los documentos cargados.
  
Para exportar un informe de evaluación:
  
- En el panel del Administrador de cumplimiento, haga clic en **Acciones** en el icono de la evaluación que quiera exportar y, después, seleccione **Exportar a Excel**.

  O bien
    
- Si está en la página de detalles de la evaluación, haga clic en el botón **Exportar a Excel**, que se encuentra en la esquina superior derecha de la página, encima de la puntuación de cumplimiento de la evaluación.
    
The assessment report will be downloaded in your browser session. If you don't see a popup informing you of this, you may wish to check your browser's downloads folder.

## <a name="archiving-an-assessment"></a>Archivar una evaluación

When you have completed an Assessment and no longer need it for compliance purposes, you can archive it. When an Assessment is archived, it is removed from Assessments dashboard.
  
> [!NOTE]
> When an Assessment is Archived, it cannot be 'unarchived' or restored to a read-write in progress state. Please note that Archived Assessments do not retain their links to uploaded evidence documents, so it is highly recommended that you perform an Export of the Assessment before archiving it, as the exported assessment report will contain links to the evidence documents, enabling you to continue to access them. 
  
Para archivar una evaluación:
  
1. En el icono de panel de la evaluación que quiera archivar, haga clic en **Acciones**. 
    
2. Seleccione **Archivar evaluación**. 
 
    Se mostrará el cuadro de diálogo **Archivar evaluaciones**, donde se le pedirá que confirme que quiere archivar la evaluación.
    
4. Para continuar con el archivado, haga clic en **Archivar**; de lo contrario, haga clic en **Cancelar**. 
    
Para ver las evaluaciones archivadas:
  
1. En el panel del Administrador de cumplimiento, active la casilla **Mostrar archivados**. 
    
    Las evaluaciones archivadas se mostrarán en una nueva sección visible debajo del resto de las evaluaciones activas, en la parte inferior de una barra titulada **Evaluaciones archivadas**.
    
3. Haga clic en el nombre de la evaluación que quiera ver.
    
Al visualizar una evaluación archivada, ninguno de los controles que pueden editarse normalmente (por ejemplo, “Implementación” o “Resultados de pruebas”) estarán activos, ni tampoco se mostrará el botón **Documentos administrados**.

## <a name="using-search"></a>Uso de la búsqueda

![Portal de confianza de servicios: Campo de búsqueda](../media/7c5cd817-3d62-420b-adb4-76e33fef941f.png)
  
Click the magnifying glass in the upper right-hand corner of the page by to expand the Search input field, enter your search terms and press Enter. The Search control will appear, with the search term in the search pane input field, and search results will appear beneath.
  
By default, Search returns Document results, and you can use the Filter By dropdown lists to refine the list of documents displayed, to add or remove search results from view. You can use multiple filter attributes at the same time to narrow the returned documents to specific cloud services, categories of compliance or security practices, regions of the world, or industries. Click the document name link to download the document.
  
![Portal de confianza de servicios: Buscar en documentos con filtro aplicado](../media/86b754e1-c63c-4514-89ac-d014bf334140.png)
  
Haga clic en el vínculo Administrador de cumplimiento para mostrar los resultados de búsqueda para los controles de evaluación del Administrador de cumplimiento. En la lista de resultados de búsqueda, se muestra la fecha en la que se creó la evaluación, el nombre de la agrupación de evaluaciones, el servicio en la nube aplicable y si los controles están administrados por Microsoft o por el cliente.
  
![Portal de confianza de servicios: Búsqueda en controles del Administrador de cumplimiento](../media/bafb811a-68ce-40b5-ad16-058498fe5439.png)
  
> [!NOTE]
> Los informes y documentos del Portal de confianza de servicios pueden descargarse como mínimo durante 12 meses después de su publicación, o bien hasta que se publique una nueva versión del documento. 
 
## <a name="localization-support"></a>Soporte de localización

Service Trust Portal enables you to view the page content in different languages. To change the page language, simply click on the globe icon in the lower left corner of the page and select the language of your choice. 
  
![Portal de confianza de servicios: Opciones de contenido localizado](../media/b50c677e-a886-4267-9eca-915d880ead7a.png)


## <a name="change-log-for-customer-managed-controls"></a>Registro de cambios de controles administrados por el cliente

El Administrador de cumplimiento se diseñó para actualizarlo de forma periódica con el fin de mantenerse al día de los cambios en los requisitos reglamentarios, así como de los cambios en nuestros servicios en la nube. En estas actualizaciones, se incluyen cambios en los Controles administrados por el cliente. Se proporciona un registro de cambios que le ayudará a comprender el impacto de estos cambios, incluidos los detalles sobre el contenido que se haya agregado o modificado, así como una guía sobre cómo afectan los cambios a las evaluaciones existentes. En general, hay dos tipos de cambio:
  
- A **Major** change is a significant change to a Customer Action, such as the addition or removal of a control or specific numbered steps, or a change in the guidance around responsibilities, recommendations, or evidence. For Major changes, we recommend that you re-evaluate your implementation and/or assessment of the affected control.
    
- A **Minor** change is an insignificant change to a Customer Actions, such as fixing a typo or formatting issues, or updating or correcting hyperlinks. Minor changes generally do not require the control to be re-evaluated; however, we do recommend that you review the updated Customer Action.
  
### <a name="customer-managed-controls---change-log-for-july-2018"></a>Controles administrados por el cliente: Registro de cambios de julio de 2018

|**Id. de control**|**Evaluación**|**Tipo de cambio**|**Descripción del cambio**|**Acciones recomendadas para clientes**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|45 C.F.R. § 164.308(a)(7)(ii)(A)<br/> |Office 365: HIPAA|Mayor|Se agregó el control de HITECH a la evaluación de HIPAA para Office 365. |Se revisaron el control agregado y las acciones de cliente recomendadas.<br/> |
|45 C.F.R.  164.312(a)(6)(ii)|Office 365: HIPAA|Mayor|Se agregó el control de HITECH a la evaluación de HIPAA para Office 365.|Se revisaron el control agregado y las acciones de cliente recomendadas.<br/>|
45 C.F.R. § 164.312(c)(1)| Office 365: HIPAA|Mayor| Se agregó el control de HITECH a la evaluación de HIPAA para Office 365. |Se revisaron el control agregado y las acciones de cliente recomendadas.<br/> |
45 C.F.R.  § 164.316(b)(2)(iii)| Office 365: HIPAA|Mayor|Se agregó el control de HITECH a la evaluación de HIPAA para Office 365.|Se revisaron el control agregado y las acciones de cliente recomendadas.<br/>|
|

### <a name="customer-managed-controls---change-log-for-april-2018"></a>Controles administrados por el cliente: Registro de cambios de abril de 2018

|**RGPD**|**HIPAA**|**ISO 27001**|**ISO 27018**|**NIST 800-53**|**NIST 800-171**|**Tipo de cambio**|**Descripción del cambio**|**Acciones recomendadas para clientes**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|6.13.2  <br/> |||C.16.1.1  <br/> |||Mayor  <br/> |La referencia numérica anterior era 6.12.1.1.  <br/> Se agregaron detalles a las recomendaciones.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
||||||3.1.6  <br/> |Mayor  <br/> |Se agregaron pasos a la guía, como habilitar la auditoría y buscar en los registros de auditoría.  <br/> |Revise las recomendaciones actualizadas en las acciones de cliente.  <br/> |
|6.8.2  <br/> |||A.10.2  <br/> |||Mayor  <br/> |La referencia numérica anterior era 6.7.2.9.  <br/> Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
|6.6.4  <br/> |45 C.F.R. § 164.312(a)(2)(i)  <br/>           45 C.F.R. § 164.312(d)  <br/> |A.9.4.2  <br/> ||IA-2  <br/> |3.5.1  <br/> |Mayor  <br/> |La referencia numérica anterior era 6.5.2.3.  <br/> Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
|6.13.1  <br/> |45 C.F.R. § 164.308(a)(1)(i)  <br/> |A.16.1  <br/> |C.16.1  <br/> |IR-4(a)  <br/> |3.6.1  <br/> |Mayor  <br/> |La referencia numérica anterior era 6.12.1.  <br/> Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
|6.7  <br/> ||||||Mayor  <br/> |La referencia numérica anterior era 6.6.1.1.  <br/> Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
|6.6.5  <br/> |||A.10.8  <br/> |IA-3  <br/> |3.5.2  <br/> |Mayor  <br/> |La referencia numérica anterior era 6.5.4.2.  <br/> Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
|6.15.1  <br/> ||||||Mayor  <br/> |La referencia numérica anterior era 6.14.1.3.  <br/> Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Vuelva a evaluar el control: revise la guía actualizada en las acciones de cliente y siga los pasos recomendados para implementar y evaluar el control.  <br/> |
|||||AC-2(h)(2)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||||AC-2(7)(b)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||||AC-2(h)(1)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
||45 C.F.R. § 164.308(a)(5)(ii)(C)  <br/> |||AC-2(g)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||||AC-2(12)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
||45 C.F.R. § 164.312(b)  <br/> |A.12.4.3  <br/> ||AU-2(d)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||||AC-2(4)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
||||||3.1.7  <br/> |Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||A.16.1.7  <br/> |C.12.4.2, parte 2  <br/> |||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||||AC-2(h)(3)  <br/> ||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||A.12.4.2  <br/> ||||Menor  <br/> |Se agregó un vínculo a la hoja Habilitar auditoría.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||A.7.2.8  <br/> ||||Menor  <br/> |Se agregaron vínculos a la hoja Búsqueda de contenido y al portal de solicitudes del interesado.  <br/> |No es necesario realizar ninguna acción.  <br/> |
||45 C.F.R. § 164.308(a)(3)(ii)(C)  <br/> |||||Menor  <br/> |Se agregaron vínculos a la hoja Habilitar auditoría y a los temas de soporte técnico del rol de administrador de Office 365.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|5.2.1  <br/> ||||||Menor  <br/> |La referencia numérica anterior era 5.2.2.  <br/> Se proporcionó información adicional en la guía sobre las responsabilidades del cliente.  <br/> |Revise las recomendaciones actualizadas en las acciones de cliente.  <br/> |
|6.11.1  <br/> |45 C.F.R. § 164.312(e)(2)(ii)  <br/> |A.10.1.1          A.10.1.2          A.18.1.5  <br/> |C.10.1.1  <br/> |SC-13  <br/> |3.13.11  <br/> |Menor  <br/> |La referencia numérica anterior era 6.10.1.2.  <br/> Se corrigió un error de escritura.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|7.5.1  <br/> ||||||Menor  <br/> |La referencia numérica anterior era A.7.4.1.  <br/> Se corrigió un error de escritura.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|||A.8.2.3  <br/> |||3.1.3  <br/> |Menor  <br/> |Se quitó una frase adicional innecesaria.  <br/> |No es necesario realizar ninguna acción.  <br/> |
||45 C.F.R. § 164.308(a)(4)(i)  <br/> |A.6.1.2  <br/> ||AC-5(a)  <br/> |3.1.2          3.1.4  <br/> |Menor  <br/> |Guía actualizada con acciones y recomendaciones adicionales.  <br/> |Revise las recomendaciones actualizadas en las acciones de cliente.  <br/> |
||45 C.F.R. § 164.308(a)(7)(ii)(E)  <br/> |||RA-2(a)  <br/> ||Menor  <br/> |Se actualizó el vínculo al tema de ayuda del servicio de importación para usar FWLink.  <br/> |No es necesario realizar ninguna acción.  <br/> |
|

### <a name="gdpr-assessment-control-id-change-reference---change-log-for-february-2018"></a>Referencia de cambio de id. de control de evaluación del RGPD: Registro de cambios de febrero de 2018 

|**Id. de control anterior (versión preliminar de noviembre de 2017)**|**Nuevo id. de control (versión disponible para el público en general de febrero de 2018)**|
|:-----|:-----|
|5.2.2  <br/> |5.2.1  <br/> |
|5.2.3  <br/> |5.2.2  <br/> |
|5.2.4  <br/> |5.2.3  <br/> |
|6.1.1.1  <br/> |6.2  <br/> |
|6.10.1.2  <br/> |6.11.1  <br/> |
|6.10.2.5  <br/> |6.11.2  <br/> |
|6.11.1.2  <br/> |6.12  <br/> |
|6.12.1  <br/> |6.13.1  <br/> |
|6.12.1.1  <br/> |6.13.2  <br/> |
|6.12.1.5  <br/> |6.13.3  <br/> |
|6.14.1.3  <br/> |6.15.1  <br/> |
|6.14.2.1  <br/> |6.15.2  <br/> |
|6.14.2.3  <br/> |6.15.3  <br/> |
|6.2.1.1  <br/> |6.3  <br/> |
|6.3.2.2  <br/> |6.4  <br/> |
|6.4.3.1  <br/> |6.5.2  <br/> |
|6.4.3.2  <br/> |6.8.1  <br/> |
|6.4.3.3  <br/> |6.5.3  <br/> |
|6.5.2  <br/> |6.6.1  <br/> |
|6.5.2.1  <br/> |6.6.2  <br/> |
|6.5.2.2  <br/> |6.6.3  <br/> |
|6.5.2.3  <br/> |6.6.4  <br/> |
|6.5.4.2  <br/> |6.6.5  <br/> |
|6.6.1.1  <br/> |6.7  <br/>   |
|6.7.2.7  <br/> |6.8.1  <br/> |
|6.7.2.9  <br/> |6.8.2  <br/> |
|6.8.1.4  <br/> |6.9.1  <br/> |
|6.8.4.1  <br/> |6.9.3  <br/> |
|6.8.4.2  <br/> |6.9.4  <br/> |
|6.9.2.1  <br/> |6.10.1  <br/>|
|6.9.2.3  <br/> |6.10.2  <br/>|
|A.7.1.1  <br/> |7.2.1  <br/> |
|A.7.1.2  <br/> |7.2.2  <br/> |
|A.7.1.3  <br/> |7.2.3  <br/> |
|A.7.1.4  <br/> |7.2.4  <br/> |
|A.7.1.5  <br/> |7.2.5  <br/> |
|A.7.1.6  <br/> |7.2.6  <br/> |
|A.7.1.7  <br/> |7.2.7  <br/> |
|A.7.2.1  <br/> |7.3.1  <br/> |
|A.7.2.10 <br/> |7.3.9  <br/> |
|A.7.2.11 <br/> |7.3.10  <br/>|
|A.7.2.2  <br/> |7.3.2  <br/> |
|A.7.2.3  <br/> |7.3.3  <br/> |
|A.7.2.4  <br/> |7.3.4  <br/> |
|A.7.2.5  <br/> |7.3.5  <br/> |
|A.7.2.6  <br/> |7.3.6  <br/> |
|A.7.2.7  <br/> |7.3.7  <br/> |
|A.7.2.8  <br/> |7.3.8  <br/> |
|A.7.3.1  <br/> |7.4.1  <br/> |
|A.7.3.10 <br/> |7.4.10  <br/>|
|A.7.3.2  <br/> |7.4.2  <br/> |
|A.7.3.3  <br/> |7.4.3  <br/> |
|A.7.3.4  <br/> |7.4.4  <br/> |
|A.7.3.5  <br/> |7.4.5  <br/> |
|A.7.3.6  <br/> |7.4.6  <br/> |
|A.7.3.7  <br/> |7.4.7  <br/> |
|A.7.3.8  <br/> |7.4.8  <br/> |
|A.7.3.9  <br/> |7.4.9  <br/> |
|A.7.4.1  <br/> |7.5.1  <br/> |
|A.7.4.2  <br/> |7.5.2  <br/> |
|A.7.4.3  <br/> |7.5.3  <br/> |
|A.7.4.4  <br/> |7.5.4  <br/> |
|A.7.4.5  <br/> |7.5.5  <br/> |
|B.8.1.1  <br/> |8.2.1  <br/> |
|B.8.1.2  <br/> |8.2.2  <br/> |
|B.8.1.3  <br/> |8.2.3  <br/> |
|B.8.1.4  <br/> |8.2.4  <br/> |
|B.8.1.5  <br/> |8.2.5  <br/> |
|B.8.1.6  <br/> |8.2.6  <br/> |
|B.8.2.1  <br/> |8.3.1  <br/> |
|B.8.3.1  <br/> |8.4.1  <br/> |
|B.8.3.2  <br/> |8.4.2  <br/> |
|B.8.3.3  <br/> |8.4.3  <br/> |
|B.8.4.1  <br/> |8.5.1  <br/> |
|B.8.4.2  <br/> |8.5.2  <br/> |
|B.8.4.3  <br/> |8.5.4  <br/> |
|B.8.4.4  <br/> |8.5.5  <br/> |
|B.8.4.5  <br/> |8.5.3  <br/> |
|B.8.4.6  <br/> |8.5.6  <br/> |
|B.8.4.7  <br/> |8.5.7  <br/> |
|B.8.4.8  <br/> |8.5.8  <br/> |
|
   
## <a name="see-also"></a>Vea también

- [Guía interactiva del Administrador de cumplimiento normativo](https://content.cloudguides.com/guides/Compliance%20Manager)

- [Anuncio de la disponibilidad general del Administrador de cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Announcing-Compliance-Manager-general-availability/ba-p/161922)

- [Microsoft 365 proporciona una estrategia de protección de la información como ayuda para el RGPD](https://blogs.office.com/2018/02/22/microsoft-365-provides-an-information-protection-strategy-to-help-with-the-gdpr)
