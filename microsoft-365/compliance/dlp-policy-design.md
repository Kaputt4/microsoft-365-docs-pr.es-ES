---
title: Diseñar una directiva de prevención de pérdida de datos
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
description: Obtenga información sobre cómo diseñar una directiva de prevención de pérdida de datos (DLP)
ms.openlocfilehash: 14e9fbb5efd20ddcf3d0a47da41a0cce89c88cee
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526324"
---
# <a name="design-a-data-loss-prevention-policy"></a>Diseñar una directiva de prevención de pérdida de datos

Tomarse el tiempo para diseñar una directiva antes de implementarla le llevará a los resultados deseados más rápido y con menos problemas no deseados, que crearla y, a continuación, ajustar solo por prueba y error. Tener los diseños de directivas documentados también le ayudará en comunicaciones, revisiones de directivas, solución de problemas y ajuste adicional.

<!--, but excessive tuning to get the intended results can be time consuming.

 if you have to do a lot of tuning to get a policy to yield the intended results can be time consuming .-->

Si es nuevo en Microsoft 365 DLP, es útil trabajar con estos artículos antes de empezar a diseñar una directiva:

- [Obtenga información sobre la prevención de pérdida](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) de datos: este artículo le presenta la disciplina de prevención de pérdida de datos y la implementación de DLP por parte de Microsoft
- [Planear la prevención de pérdida de datos (DLP):](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) al trabajar con este artículo, podrá:
    - [Identificar partes interesadas](dlp-overview-plan-for-dlp.md#identify-stakeholders)
    - [Describir las categorías de información confidencial que se protegerán](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
    - [Establecer objetivos y estrategia](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
- [Referencia de directiva de prevención](dlp-policy-reference.md#data-loss-prevention-policy-reference) de pérdida de datos: en este artículo se presentan todos los componentes de una directiva DLP y cómo cada uno influye en el comportamiento de una directiva

## <a name="policy-design-overview"></a>Introducción al diseño de directivas

[El diseño de una directiva se](#policy-design-process) trata principalmente de definir claramente sus necesidades empresariales, documentarlas en una instrucción de intención de directiva y, [a](#define-intent-for-the-policy) continuación, [asignarlas a la configuración de directivas](#map-business-needs-to-policy-configuration). Usará las decisiones que ha tomado en la fase de planeación para informar de algunas de las decisiones de diseño de directivas. 

### <a name="define-intent-for-the-policy"></a>Definir la intención de la directiva 

Debería poder resumir la intención empresarial de cada directiva que tenga en una sola instrucción. El desarrollo de esta instrucción impulsará las conversaciones de la organización y, cuando se desarrolle completamente, esta instrucción vincula directamente la directiva con un propósito empresarial y proporciona una guía básica para el diseño de directivas. Los pasos del artículo [Plan for data loss prevention (DLP)](dlp-overview-plan-for-dlp.md#overview-of-planning-process) le ayudarán a empezar a usar la instrucción de propósito de la directiva.  

Recuerde en [dlp policy configuration overview](dlp-learn-about-dlp.md#dlp-policy-configuration-overview) that all DLP policies require that you:

- Elegir lo que desea supervisar
- Elegir dónde desea supervisar
- Elija las condiciones que deben coincidir para que una directiva se aplique a un elemento
- Elegir la acción que se debe realizar cuando se cumplen las condiciones de la directiva 

Por ejemplo, este es un primer borrador ficticio de una instrucción intent que proporciona respuestas a las cuatro preguntas: 

*"Somos una organización con sede en Estados Unidos Office y debemos detectar documentos que contienen información confidencial de atención médica cubierta por HIPPA que se almacenan en OneDrive/SharePoint y proteger contra esa información que se comparte en mensajes de chat y canal y restringir Teams que todos compartan con terceros no autorizados".* 

A medida que desarrolle un diseño de directiva, es probable que modifique y extienda la instrucción.

### <a name="map-business-needs-to-policy-configuration"></a>Asignar las necesidades empresariales a la configuración de directivas

Vamos a dividir la instrucción de borrador de ejemplo hacia abajo y asignarla a puntos de configuración de directiva DLP.

|Instrucción  |Respuesta a la pregunta de configuración y asignación de configuración  |
|---------|---------|
| "Somos una organización con sede en Estados Unidos y debemos detectar documentos Office que contienen información confidencial de atención médica cubierta por HIPPA...  |- **Qué supervisar**: Office documentos, use la plantilla ley de seguros de salud [(HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) de Estados Unidos </br>- Condiciones para una coincidencia: (preconfigurada pero editable): el elemento contiene el número del SSN y la Agencia antidrogas (DEA) de ESTADOS UNIDOS, clasificación internacional de las enfermedades (ICD-9-CM), clasificación internacional de las enfermedades (ICD-10-CM), el contenido se comparte con personas ajenas **a** mi organización.  </br> - impulsa las conversaciones para aclarar el umbral de activación para la [detección, como](sensitive-information-type-learn-about.md#more-on-confidence-levels) los niveles de confianza [, y el](dlp-policy-reference.md#content-contains) recuento de instancias (denominado tolerancia a fugas).|
|... que se almacenan en OneDrive/SharePoint y protegen contra esa información que se comparte Teams chat y mensajes de canal... |- **Dónde supervisar**: [ámbito de](dlp-policy-reference.md#locations) ubicación incluyendo o excluyendo OneDrive y SharePoint sitios y Teams cuentas de chat/canal o grupos de distribución. |
|... y restringir que todos compartan esos elementos con terceros no autorizados".  | - **Acciones que se deben realizar**: [agregar restringir el](dlp-policy-reference.md#actions) *acceso o cifrar el contenido en Microsoft 365 ubicación* </br> - impulsa la conversación sobre qué acciones tomar cuando se desencadena una directiva, incluidas acciones de protección como restricciones de uso compartido, acciones de reconocimiento como notificaciones y alertas, y acciones de habilitación del usuario como permitir invalidaciones de usuario de una acción de bloqueo |

En este ejemplo no se cubren todos los puntos de configuración de una directiva DLP, tendría que expandirse. Pero debería hacer que piense en la dirección correcta a medida que desarrolle sus propias instrucciones de propósito de directiva DLP.

> [!IMPORTANT]
> Ten en cuenta que las ubicación(s) que eliges afectan si puedes usar tipos de información confidencial, etiquetas de confidencialidad y etiquetas de retención, así como las acciones disponibles. Consulte Referencia [de directiva de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference).

## <a name="policy-design-process"></a>Proceso de diseño de directivas

1. Complete los pasos descritos en:
    1. [Planear la prevención de pérdida de datos (DLP):](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) al trabajar con este artículo, podrá:
        1. [Identifique las partes interesadas](dlp-overview-plan-for-dlp.md#identify-stakeholders)
        1. [Describir las categorías de información confidencial que se protegerán](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
        1. [Establecer objetivos y estrategia](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
        1. [Definir el plan de implementación de directivas](dlp-overview-plan-for-dlp.md#policy-deployment)

1. Familiarícese con la [referencia](dlp-policy-reference.md#data-loss-prevention-policy-reference) de directiva de prevención de pérdida de datos para que comprenda todos los componentes de una directiva DLP y cómo cada uno influye en el comportamiento de una directiva.

1. Familiarícese con [lo que incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md#what-the-dlp-policy-templates-include).

1. Desarrolle la declaración de intenciones de directiva con las partes interesadas clave. Consulte el ejemplo anterior de este artículo.

1. Determine cómo se ajusta esta directiva a su estrategia de directiva DLP general.

> [!IMPORTANT]
> No se puede cambiar el nombre de las directivas una vez creadas. Si debe cambiar el nombre de una directiva, tendrá que crear una nueva con el nombre deseado y retirar la anterior. Así que decide la estructura de nomenclatura que usarán todas las directivas ahora. 

6. Asigne los elementos de la instrucción de propósito de directiva a las opciones de configuración.

7. Decide desde qué plantilla de directiva empezarás, predefinida o personalizada.

8. Vaya a través de la plantilla y reúna toda la información necesaria antes de crear la directiva. Es probable que encuentre que hay algunos puntos de configuración que no se tratan en la instrucción de intención de directiva. Eso está bien. Vuelva a las partes interesadas para averiguar los requisitos de los puntos de configuración que faltan. 

9. Documente la configuración de todas las opciones de directiva y repase con las partes interesadas. Puede volver a usar la asignación de la instrucción de propósito de directiva a los puntos de configuración, que ahora está totalmente ensalzado.

10. [Cree un borrador](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy) de directiva y vuelva a consultar el plan [de implementación de directivas](dlp-overview-plan-for-dlp.md#policy-deployment) .

<!--## Policy design examples

|Customer business needs description  | approach  |
|---------|---------|
|**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations. </br> - knows which types of sensitive information are top priority. </br> - must minimize business disruption as policies are rolled out. </br> -  has IT resources and can hire experts to help plan, design deploy </br> - has a premier support contract with Microsoft| - Take the time to understand what regulations they must comply with and how they are going to comply. </br> -Take the time to understand the better together value of the Microsoft 365 Information Protection stack </br> - Develop sensitivity labeling scheme for prioritized items and apply </br> - Involve business process owners </br>- Design/code policies, deploy in test mode, train users </br>- repeat|
|**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth. They use Teams, OneDrive for Business and Exchange extensively.     |- Start with simple policies on the prioritized locations. </br>- Monitor what gets identified </br>- Apply sensitivity labels accordingly </br>- Refine policies, train users       |
|**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly. They are willing to dedicate some resources, but can't afford to hire outside experts. </br>- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint </br>- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items </br>- Employees value speed of work over data protection discipline </br>- Customer splurged and bought all 18 employees new Windows 10 devices     |- Take advantage of the default DLP policy in Teams </br>- Use restricted by default setting for SharePoint items </br>- Deploy policies that prevent external sharing </br>- Deploy policies to prioritized locations </br>- Deploy policies to Windows 10 devices </br>- Block uploads to non-OneDrive for Business cloud storage      |


1. For example:
    1. Identify your volume thresholds that your company deems to be low-risk (leakage tolerance), perhaps from unintentional sharing and is an opportunity to educate users and the threshold that is concerning or high-risk for your company that may need immediate attention.
    - example volume: “Low risk” for Contoso is 1 credit card number, perhaps it was a personal card that was shared carelessly
    - example volume: “High risk” for Contoso is 2 or more credit card numbers. It doesn’t feel like a common scenario that an employee would engage in accidentally



–   For each of the sensitive information types listed out, list out **who should have access to that data when it’s generated** and **what type of activities should be allowable with that data**


  <!--(Perhaps this is where we can provide some basic categories, templates, activities and actions that are supported by Microsoft. Some of these items are not discoverable until you are deeper within a policy creation flow. If we provide, we should time stamp it for “last updated” or “as of xx/xx/xxx”)
–   (Show table with parent-child relationships between categories, templates and sensitive info types that Microsoft supports) Should be gathered from GA Compliance environment-->

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

|Statement  |Configuration question answered and configuration mapping  |
|---------|---------|
| We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information...|- **What to monitor**: All available item types, use the [U.S. Health Insurance Act (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) template. </br>- **Conditions for a match**: (preconfigured but editable) - item contains full names, physical addresses, driver's license number, U.S. SSN
| ...and prevent it from egressing outside of our company’s borders... |- **Actions to take**: Block anyone outside the organization from accessing items, block unintentional sharing by internal users with anyone outside the org.|
|...We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices...| - **Actions to take**: - Block access to items, block all activities (upload to cloud, copy to clipboard, copy to USB, copy to network share, access by restricted app, print, copy/move via Bluetooth, copy/move via remote desktop) from Windows devices.  </br> - **Where to monitor**: in all Microsoft 365 locations
| ...We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item....| - **Conditions for a match**: (preconfigured but editable) any single item contains more than one of these or any two or more of these:  Full Name, U.S. Social Security Number, Drug Enforcement Agency (DEA) number, International Classification of Diseases (ICD-9-CM), International Classification of Diseases (ICD-10-CM), Physical Address, U.S. driver's license number. For example, two instanced of Full Name or one instance of a U.S. Social Security Number along with one instance of Drug Enforcement Agency (DEA) number will trigger a match.

   , content is shared with people outside my organization  </br> - drives conversations to clarify the triggering threshold for detection like [confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels), and [instance count](dlp-policy-reference.md#content-contains) (called leakage tolerance).|
|...that are stored in OneDrive/SharePoint and protect against that information being shared Teams chat and channel messages... |- **Where to monitor**:  [Location scoping](dlp-policy-reference.md#locations) by including or excluding OneDrive and SharePoint sites and Teams chat/channel accounts or distribution groups. |
|...and restrict everyone from sharing those items with unauthorized third parties."  | - **Actions to take**: [You add](dlp-policy-reference.md#actions) *Restrict access or encrypt the content in Microsoft 365 locations* </br> - drives conversation on what actions to take when a policy is triggered including protective actions like sharing restrictions, awareness actions like notifications and alerts, and user empowerment actions like allow user overrides of a blocking action |

-->


## <a name="see-also"></a>Vea también

- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference)
- [Referencia de sugerencias de directiva de prevención de pérdida de datos](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)