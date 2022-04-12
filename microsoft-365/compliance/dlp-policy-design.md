---
title: Diseño de una directiva de prevención de pérdida de datos
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
description: Aprenda a diseñar una directiva de prevención de pérdida de datos (DLP)
ms.openlocfilehash: 2d7c370ab34eea2c708769674495a2c51f1a3fcf
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782047"
---
# <a name="design-a-data-loss-prevention-policy"></a>Diseño de una directiva de prevención de pérdida de datos

Tomarse el tiempo necesario para diseñar una directiva antes de implementarla le llevará a los resultados deseados más rápido y con menos problemas no deseados, que crearla y, a continuación, ajustarla solo por prueba y error. La documentación de los diseños de directivas también le ayudará en comunicaciones, revisiones de directivas, solución de problemas y optimización adicional.

<!--, but excessive tuning to get the intended results can be time consuming.

 if you have to do a lot of tuning to get a policy to yield the intended results can be time consuming .-->

Si no está familiarizado con Microsoft 365 DLP, es útil trabajar con estos artículos antes de empezar a diseñar una directiva:

- [Más información sobre la prevención de pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) : en este artículo se presenta la materia de prevención de pérdida de datos y la implementación de DLP por parte de Microsoft.
- [Planear la prevención de pérdida de datos (DLP):](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) al trabajar en este artículo, podrá:
  - [Identificación de las partes interesadas](dlp-overview-plan-for-dlp.md#identify-stakeholders)
  - [Describir las categorías de información confidencial que se van a proteger](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
  - [Establecer objetivos y estrategias](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
- Referencia de directiva [de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference): en este artículo se presentan todos los componentes de una directiva DLP y cómo influye cada uno en el comportamiento de una directiva.

## <a name="policy-design-overview"></a>Información general sobre el diseño de directivas

[Diseñar una directiva](#policy-design-process) consiste principalmente en definir claramente [las necesidades empresariales, documentarlas en una declaración de intención de directiva](#define-intent-for-the-policy) y, a continuación, [asignarlas a la configuración de directivas](#map-business-needs-to-policy-configuration). Usará las decisiones que tomó en la fase de planeación para informar de algunas de las decisiones de diseño de directivas.

### <a name="define-intent-for-the-policy"></a>Definición de la intención de la directiva

Debería poder resumir la intención empresarial de cada directiva que tenga en una sola instrucción. El desarrollo de esta declaración impulsará las conversaciones en su organización y, cuando se completa, esta declaración vincula directamente la directiva a un propósito empresarial y proporciona una hoja de ruta para el diseño de directivas. Los pasos del artículo [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md#overview-of-planning-process) le ayudarán a empezar a trabajar en la instrucción de intención de directiva.

Recuerde en [la introducción a la configuración de directivas DLP](dlp-learn-about-dlp.md#dlp-policy-configuration-overview) que todas las directivas DLP requieren lo siguiente:

- Elegir lo que quiere supervisar
- Elija dónde desea supervisar
- Elija las condiciones que deben coincidir para que una directiva se aplique a un elemento.
- Elija la acción que debe realizarse cuando se cumplan las condiciones de la directiva.

Por ejemplo, este es un primer borrador ficticio de una instrucción de intención que proporciona respuestas a las cuatro preguntas:

*"Somos una organización con sede en Ee. UU., y debemos detectar Office documentos que contienen información confidencial de atención médica cubierta por HIPPA que se almacenan en OneDrive/SharePoint y proteger contra esa información que se comparte en Teams mensajes de chat y canal, y impedir que todos los usuarios los compartan con terceros no autorizados".*

A medida que desarrolle un diseño de directiva, es probable que modifique y extienda la instrucción.

### <a name="map-business-needs-to-policy-configuration"></a>Asignación de las necesidades empresariales a la configuración de directivas

Vamos a desglosar la instrucción de borrador de ejemplo y asignarla a puntos de configuración de directiva DLP.

|Instrucción|Pregunta de configuración respondida y asignación de configuración|
|---|---|
|"Somos una organización con sede en Ee. UU., y necesitamos detectar Office documentos que contienen información confidencial de atención médica cubierta por HIPPA...|- **Qué supervisar**: Office documentos, use la plantilla de la Ley de [seguros de salud (HIPAA) de EE. UU.](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) </br>- **Condiciones para una coincidencia**: (preconfigurado pero modificable): el elemento contiene el número de la SSN estadounidense y la Agencia antidrogas (DEA), clasificación internacional de enfermedades (ICD-9-CM), clasificación internacional de enfermedades (ICD-10-CM), el contenido se comparte con personas ajenas a mi organización.  </br> : impulsa las conversaciones para aclarar el umbral desencadenante para la detección, como [los niveles de confianza](sensitive-information-type-learn-about.md#more-on-confidence-levels), y el [recuento de instancias](dlp-policy-reference.md#content-contains) (denominado tolerancia a fugas).|
|... que se almacenan en OneDrive/SharePoint y protegen contra esa información que se comparte Teams mensajes de chat y canales...|- **Dónde supervisar**: [ámbito de la ubicación](dlp-policy-reference.md#locations) mediante la inclusión o exclusión de OneDrive y SharePoint sitios y Teams cuentas de chat o canal o grupos de distribución.|
|... y impedir que todos compartan esos elementos con terceros no autorizados".|- **Acciones que debe realizar**: [agregue](dlp-policy-reference.md#actions) *Restringir el acceso o cifrar el contenido en Microsoft 365 ubicaciones* </br> : impulsa la conversación sobre las acciones que se deben realizar cuando se desencadena una directiva, incluidas acciones de protección, como restricciones de uso compartido, acciones de reconocimiento como notificaciones y alertas, y acciones de empoderamiento del usuario, como permitir invalidaciones de usuario de una acción de bloqueo.|

En este ejemplo no se tratan todos los puntos de configuración de una directiva DLP, tendría que expandirse. Pero debería hacer que piense en la dirección correcta a medida que desarrolle sus propias instrucciones de intención de directiva DLP.

> [!IMPORTANT]
> Tenga en cuenta que las ubicaciones que elija afectarán a si puede usar tipos de información confidencial, etiquetas de confidencialidad y etiquetas de retención, así como las acciones que están disponibles. Consulte referencia de directiva [de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference).

## <a name="policy-design-process"></a>Proceso de diseño de directivas

1. Complete los pasos [descritos en Planear la prevención de pérdida de datos (DLP):](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) para ello, siga estos pasos:
   1. [Identifique las partes interesadas](dlp-overview-plan-for-dlp.md#identify-stakeholders)
   1. [Describir las categorías de información confidencial que se van a proteger](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
   1. [Establecer objetivos y estrategias](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
   1. [Definición del plan de implementación de directivas](dlp-overview-plan-for-dlp.md#policy-deployment)

2. Familiarícese con la referencia de directiva [de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference) para comprender todos los componentes de una directiva DLP y cómo influye cada uno en el comportamiento de una directiva.

3. Familiarícese con [lo que incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md#what-the-dlp-policy-templates-include).

4. Desarrolle la declaración de intenciones de la directiva con las partes interesadas clave. Consulte el ejemplo anterior de este artículo.

5. Determine cómo encaja esta directiva en su estrategia de directiva DLP general.

   > [!IMPORTANT]
   > No se puede cambiar el nombre de las directivas una vez creadas. Si debe cambiar el nombre de una directiva, tendrá que crear una nueva con el nombre deseado y retirar la anterior. Por lo tanto, decida la estructura de nomenclatura que todas las directivas usarán ahora.

6. Asigne los elementos de la instrucción de intención de directiva a las opciones de configuración.

7. Decida desde qué plantilla de directiva va a empezar, predefinida o personalizada.

8. Consulte la plantilla y reúna toda la información necesaria antes de crear la directiva. Es probable que descubra que hay algunos puntos de configuración que no se tratan en la instrucción de intención de directiva. Eso está bien. Volver a las partes interesadas para establecer los requisitos de los puntos de configuración que faltan.

9. Documente la configuración de todas las opciones de directiva y revíselas con las partes interesadas. Puede volver a usar la asignación de la instrucción de intención de directiva a los puntos de configuración, que ahora está totalmente completo.

10. [Cree un](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy) borrador de directiva y refiérase al plan de [implementación de directivas](dlp-overview-plan-for-dlp.md#policy-deployment) .

<!--## Policy design examples

|Customer business needs description|approach|
|---|---|
|**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations. </br> - knows which types of sensitive information are top priority. </br> - must minimize business disruption as policies are rolled out. </br> -  has IT resources and can hire experts to help plan, design deploy </br> - has a premier support contract with Microsoft|- Take the time to understand what regulations they must comply with and how they are going to comply. </br> -Take the time to understand the better together value of the Microsoft 365 Information Protection stack </br> - Develop sensitivity labeling scheme for prioritized items and apply </br> - Involve business process owners </br>- Design/code policies, deploy in test mode, train users </br>- repeat|
|**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth. They use Teams, OneDrive for Business and Exchange extensively.|- Start with simple policies on the prioritized locations. </br>- Monitor what gets identified </br>- Apply sensitivity labels accordingly </br>- Refine policies, train users|
|**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly. They are willing to dedicate some resources, but can't afford to hire outside experts. </br>- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint </br>- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items </br>- Employees value speed of work over data protection discipline </br>- Customer splurged and bought all 18 employees new Windows 10 devices|- Take advantage of the default DLP policy in Teams </br>- Use restricted by default setting for SharePoint items </br>- Deploy policies that prevent external sharing </br>- Deploy policies to prioritized locations </br>- Deploy policies to Windows 10 devices </br>- Block uploads to non-OneDrive for Business cloud storage|

1. For example:
    1. Identify your volume thresholds that your company deems to be low-risk (leakage tolerance), perhaps from unintentional sharing and is an opportunity to educate users and the threshold that is concerning or high-risk for your company that may need immediate attention.
    - example volume: “Low risk” for Contoso is 1 credit card number, perhaps it was a personal card that was shared carelessly
    - example volume: “High risk” for Contoso is 2 or more credit card numbers. It doesn’t feel like a common scenario that an employee would engage in accidentally

– For each of the sensitive information types listed out, list out **who should have access to that data when it’s generated** and **what type of activities should be allowable with that data**

  <!--(Perhaps this is where we can provide some basic categories, templates, activities and actions that are supported by Microsoft. Some of these items are not discoverable until you are deeper within a policy creation flow. If we provide, we should time stamp it for “last updated” or “as of xx/xx/xxx”)
– (Show table with parent-child relationships between categories, templates and sensitive info types that Microsoft supports) Should be gathered from GA Compliance environment-->

<!--

> [!TIP] The more locations you include ensures broader application of the policy and more consistent coverage. If you include locations that are mostly used for internal collaboration, the responsiveness of collaboration may be impacted.

- whether the protective actions you need are supported throught the associated location or if you need to compromise to extend coverage
    - also usefule for identifying the most restrictive actions available
    - (we shouldn't mention here that the "content contains" condition is the primary staple for a DLP policy and should be utilized as a starting point for policy creation. The other workload-specific conditions can be ustilized as an extended or granular control of company's DLP policy. Useful for when "too much" data is being restricted and known sensitive data typically falls under certain conditions.)
    - (We can mention here that their quantitative goal such as "protect X% of data across all locations while maintaining x productivity" can be monitored throught alerts or reports. If protection is too high of working against their established goals, they can come back to policy and tweak their conditions/actions)
- Finally, you should have a union of what, hwo and when to be covered which will easily map to generating a live policy via Microsoft DLP.
-
5. At this stage you should asses how you should start this policy. ***LINK OUT TO DEPLOYING A POLICY COVERED IN THE PLANNING TOPIC TOO***
    - Test: your company is very large, conservative or the actions established are pretty restrictive
    - Test w/ notifications: same as above, but you get to test out investigation cadence or volume
    - Live: immediately start this policy in your environment. Useful for when data protection is needed immediately, such as a reactive policy creation, or if you're confident in your planning, or if the risk is low (liek audit actions, etc.)
    - keep it off:
-->

<!--## Policy Design Examples

Here are some examples of more detailed policy intent statement to configuration mappings.

*We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information and prevent it from egressing outside of our company’s borders. We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices. We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item. We have a Microsoft 365 E5 subscription and want to protect all locations and first party apps that are available to us because we can’t afford to have any data leaks. If an event occurs or is prevented, we want to alert our compliance admin and educate our end-users where necessary.*

|Statement|Configuration question answered and configuration mapping|
|---|---|
|We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information...|- **What to monitor**: All available item types, use the [U.S. Health Insurance Act (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) template. </br>- **Conditions for a match**: (preconfigured but editable) - item contains full names, physical addresses, driver's license number, U.S. SSN
|...and prevent it from egressing outside of our company’s borders...|- **Actions to take**: Block anyone outside the organization from accessing items, block unintentional sharing by internal users with anyone outside the org.|
|...We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices...|- **Actions to take**: - Block access to items, block all activities (upload to cloud, copy to clipboard, copy to USB, copy to network share, access by restricted app, print, copy/move via Bluetooth, copy/move via remote desktop) from Windows devices.  </br> - **Where to monitor**: in all Microsoft 365 locations
|...We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item....|- **Conditions for a match**: (preconfigured but editable) any single item contains more than one of these or any two or more of these:  Full Name, U.S. Social Security Number, Drug Enforcement Agency (DEA) number, International Classification of Diseases (ICD-9-CM), International Classification of Diseases (ICD-10-CM), Physical Address, U.S. driver's license number. For example, two instanced of Full Name or one instance of a U.S. Social Security Number along with one instance of Drug Enforcement Agency (DEA) number will trigger a match.

   , content is shared with people outside my organization  </br> - drives conversations to clarify the triggering threshold for detection like [confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels), and [instance count](dlp-policy-reference.md#content-contains) (called leakage tolerance).|
|...that are stored in OneDrive/SharePoint and protect against that information being shared Teams chat and channel messages...|- **Where to monitor**:  [Location scoping](dlp-policy-reference.md#locations) by including or excluding OneDrive and SharePoint sites and Teams chat/channel accounts or distribution groups.|
|...and restrict everyone from sharing those items with unauthorized third parties."|- **Actions to take**: [You add](dlp-policy-reference.md#actions) *Restrict access or encrypt the content in Microsoft 365 locations* </br> - drives conversation on what actions to take when a policy is triggered including protective actions like sharing restrictions, awareness actions like notifications and alerts, and user empowerment actions like allow user overrides of a blocking action|

-->

## <a name="see-also"></a>Consulta también

- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference)
- [Referencia de sugerencias de directiva de prevención de pérdida de datos](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)