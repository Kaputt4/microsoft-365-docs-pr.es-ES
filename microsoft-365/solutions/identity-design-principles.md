---
title: 'A la identidad y más allá: punto de vista de un arquitecto'
description: Obtenga información sobre las principales estrategias de diseño para la arquitectura de Microsoft Enterprise de Alex Shteynberg, arquitecto principal técnico de Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: bd2aaa7bcb6321255f7ab83b7a04865152d30f8d
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986298"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>A la identidad y más allá: punto de vista de un arquitecto

En este artículo, [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), arquitecto técnico principal de Microsoft, describe las principales estrategias de diseño para las organizaciones empresariales que adoptan Microsoft 365 y otros servicios en la nube de Microsoft.

## <a name="about-the-author"></a>Acerca del autor

![Foto de Alex Shteynberg.](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Soy arquitecto técnico principal en el [Centro tecnológico de Microsoft](https://www.microsoft.com/mtc?rtc=1) de Nueva York. Trabajo principalmente con clientes grandes y requisitos complejos. Mi punto de vista y mis opiniones se basan en estas interacciones y es posible que no se apliquen a todas las situaciones. Sin embargo, en mi experiencia, si podemos ayudar a los clientes con los desafíos más complejos, podemos ayudar a todos los clientes.

Normalmente trabajo con más de 100 clientes cada año. Aunque todas las organizaciones tienen características únicas, es interesante ver tendencias y aspectos comunes. Por ejemplo, una tendencia es el interés entre sectores para muchos clientes. Después de todo, una sucursal bancaria también puede ser una cafetería y un centro comunitario.

En mi rol, me centraré en ayudar a los clientes a llegar a la mejor solución técnica para abordar su conjunto único de objetivos empresariales. Oficialmente, me concentro en la identidad, la seguridad, la privacidad y el cumplimiento. Me encanta el hecho de que toquen todo lo que hacemos. Me da la oportunidad de participar en la mayoría de los proyectos. Esta actividad me mantiene ocupado y disfrutando de este rol.

Vivo en la ciudad de Nueva York (el mejor!) y realmente disfrutar de la diversidad de su cultura, comida, y personas (no tráfico). Me encanta viajar cuando puedo y espero ver la mayor parte del mundo en mi vida. Estoy investigando un viaje a África para aprender sobre la vida silvestre.

## <a name="guiding-principles"></a>Principios rectores

- **Simple suele ser mejor**: puede hacer (casi) cualquier cosa con tecnología, pero no significa que deba hacerlo. Especialmente en el espacio de seguridad, muchos clientes sobreingeniería soluciones. Me gusta [este vídeo](https://www.youtube.com/watch?v=SOQgABDSYZE) de la conferencia stripe de Google para subrayar este punto.
- **Personas, proceso, tecnología**: [diseñe para que las personas](https://en.wikipedia.org/wiki/Human-centered_design) mejoren el proceso, no la tecnología primero. No hay soluciones "perfectas". Necesitamos equilibrar varios factores de riesgo y las decisiones serán diferentes para cada negocio. Demasiados clientes diseñan un enfoque que sus usuarios evitarán más adelante.
- **Céntrese en "por qué" primero y "cómo" más tarde**: Sea el molesto niño de 7 años con un millón de preguntas. No podemos llegar a la respuesta correcta si no conocemos las preguntas adecuadas. Muchos clientes hacen suposiciones sobre cómo deben funcionar las cosas en lugar de definir el problema empresarial. Siempre hay varias rutas de acceso que se pueden tomar.
- **Larga cola de procedimientos recomendados anteriores**: reconozca que los procedimientos recomendados cambian a velocidad de luz. Si ha examinado Azure AD hace más de tres meses, es probable que esté obsoleto. Todo esto está sujeto a cambios después de la publicación. La opción "Mejor" hoy puede no ser la misma en seis meses.

## <a name="baseline-concepts"></a>Conceptos de línea base

No omita esta sección. A menudo encuentro que debo dar un paso atrás en estos artículos, incluso para los clientes que han estado usando servicios en la nube durante años.
Por desgracia, el lenguaje no es una herramienta precisa. A menudo usamos la misma palabra para significar conceptos diferentes o palabras diferentes para significar el mismo concepto. A menudo uso este diagrama siguiente para establecer cierta terminología de línea base y "modelo de jerarquía".
<br><br>

![Ilustración del inquilino, la suscripción, el servicio y los datos.](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)

<br>

Cuando aprendes a nadar, es mejor empezar en la piscina y no en medio del océano. No estoy tratando de ser técnicamente preciso con este diagrama. Es un modelo para analizar algunos conceptos básicos.

En el diagrama:

- Tenant = una instancia de Azure AD. Se encuentra en la "parte superior" de una jerarquía o en el nivel 1 del diagrama. Podemos considerar este nivel como el "[límite](/azure/active-directory/users-groups-roles/licensing-directory-independence)" donde se produce todo lo demás ([aparte de Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) ). Todos los servicios en la nube empresarial de Microsoft forman parte de uno de estos inquilinos. Los servicios de consumidor son independientes. "Inquilino" aparece en la documentación como Office 365 inquilino, inquilino de Azure, inquilino de WVD, etc. A menudo encuentro que estas variaciones causan confusión a los clientes.
- Los servicios o suscripciones, nivel 2 del diagrama, pertenecen a un solo inquilino. La mayoría de los servicios SaaS son 1:1 y no se pueden mover sin migración. Azure es diferente, puede [mover la facturación](/azure/cost-management-billing/manage/billing-subscription-transfer) o una [suscripción](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) a otro inquilino. Hay muchos clientes que necesitan mover suscripciones de Azure. Este escenario tiene varias implicaciones. Los objetos que existen fuera de la suscripción no se mueven. Por ejemplo, el control de acceso basado en rol (Azure RBAC), los objetos de Azure AD (grupos, aplicaciones, directivas, etc.) y algunos servicios (Azure Key Vault, Data Bricks, etc.). No migre servicios sin una buena necesidad empresarial. Algunos scripts que pueden resultar útiles para la migración se [comparten en GitHub](https://github.com/lwajswaj/azure-tenant-migration).
- Un servicio determinado suele tener algún tipo de límite de "subnivel" o nivel 3 (L3). Este límite es útil para comprender la segregación de la seguridad, las directivas, la gobernanza, etc. Desafortunadamente, no conozco ningún nombre uniforme. Algunos ejemplos de nombres para L3 son: Suscripción de Azure = [recurso](/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instancia](/dynamics365/admin/new-instance-management); Power BI = [área de trabajo](/power-bi/service-create-the-new-workspaces); Power Apps = [entorno](/power-platform/admin/environments-overview); y así sucesivamente.
- El nivel 4 es donde residen los datos reales. Este "plano de datos" es un artículo complejo. Algunos servicios usan Azure AD para RBAC, otros no. Lo analizaré un poco cuando lleguemos a los artículos de delegación.

Algunos conceptos adicionales que encuentro que muchos clientes (y empleados de Microsoft) se confunden o tienen preguntas sobre incluyen los siguientes problemas:

- Cualquier persona puede [crear](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) muchos inquilinos [sin costo](https://azure.microsoft.com/pricing/details/active-directory/) alguno. No necesita un servicio aprovisionado dentro de él. Tengo docenas. Cada nombre de inquilino es único en el servicio en la nube mundial de Microsoft (es decir, no hay dos inquilinos que puedan tener el mismo nombre). Todos están en el formato de TenantName.onmicrosoft.com. También hay procesos que crean inquilinos automáticamente ([inquilinos no administrados](/azure/active-directory/users-groups-roles/directory-self-service-signup)). Por ejemplo, esto puede ocurrir cuando un usuario se registra en un servicio empresarial con un dominio de correo electrónico que no existe en ningún otro inquilino.
- En un inquilino administrado, muchos [dominios DNS](/azure/active-directory/fundamentals/add-custom-domain) se pueden registrar en él. Esto no cambia el nombre del inquilino original. Actualmente no hay ninguna manera fácil de cambiar el nombre de un inquilino (aparte de la migración). Aunque el nombre del inquilino técnicamente no es crítico en estos días, algunos pueden encontrar que esto está limitando.
- Debe reservar un nombre de inquilino para su organización aunque aún no tenga previsto implementar ningún servicio. De lo contrario, alguien puede tomarlo de usted y no hay ningún proceso sencillo para recuperarlo (el mismo problema que los nombres DNS). He oído esto demasiado a menudo por parte de los clientes. El nombre de su inquilino también debe ser un artículo de debate.
- Si posee espacios de nombres DNS, debe agregarlos todos a los inquilinos. De lo contrario, se podría crear un [inquilino no administrado](/azure/active-directory/users-groups-roles/directory-self-service-signup) con este nombre, lo que provoca una interrupción para [que se administre](/azure/active-directory/users-groups-roles/domains-admin-takeover).
- El espacio de nombres DNS (por ejemplo, contoso.com) puede pertenecer a un solo inquilino. Esto tiene implicaciones para varios escenarios (por ejemplo, compartir un dominio de correo electrónico durante una fusión o adquisición, etc.). Hay una manera de registrar un sub DNS (por ejemplo, div.contoso.com) en un inquilino diferente, pero eso se debe evitar. Al registrar un nombre de dominio de nivel superior, se supone que todos los subdominios pertenecen al mismo inquilino. En escenarios multiinquilino (vea a continuación) normalmente recomendaría usar otro nombre de dominio de nivel superior (como contoso.ch o ch-contoso.com).
- ¿Quién debe "poseer" un inquilino? A menudo veo clientes que no saben quién es el propietario de su inquilino. Esta falta de conocimiento es una gran marca roja. Llame al soporte técnico de Microsoft lo antes posible. Igual de problemático es cuando un propietario de servicio (a menudo un administrador de Exchange) se designa para administrar un inquilino. El inquilino contendrá todos los servicios que quiera en el futuro. El propietario del inquilino debe ser un grupo que pueda tomar decisiones para habilitar todos los servicios en la nube de una organización. Otro problema es cuando se pide a un grupo de propietarios de inquilinos que administre todos los servicios. Esto no se escala para organizaciones grandes.
- No hay ningún concepto de subinquilino o superinquilino. Por alguna razón, este mito se repite a sí mismo. Esto también se aplica a los inquilinos de [Azure AD B2C](/azure/active-directory-b2c/) . Oigo demasiadas veces: "Mi entorno B2C está en mi inquilino XYZ" o "Cómo mover mi inquilino de Azure a mi inquilino de Office 365?"
- Este documento se centra principalmente en la nube comercial en todo el mundo, porque eso es lo que usan la mayoría de los clientes. A veces resulta útil conocer las [nubes soberanas](/azure/active-directory/develop/authentication-national-cloud). Las nubes soberanas tienen implicaciones adicionales para analizar cuáles están fuera del ámbito de esta discusión.

## <a name="baseline-identity-articles"></a>Artículos de identidad de línea base

Hay mucha documentación sobre la plataforma de identidad de Microsoft: Azure Active Directory (Azure AD). Para aquellos que están empezando, a menudo se siente abrumador. Incluso después de aprender al respecto, mantenerse al día con la innovación y el cambio constantes puede ser un desafío. En mis interacciones con los clientes a menudo me encuentro como "traductor" entre los objetivos empresariales y los enfoques "Bueno, Mejor, Mejor" para abordarlos (y "notas de acantilado" humanas para estos artículos). Rara vez hay una respuesta perfecta y la decisión "correcta" es un equilibrio de varios factores de riesgo. A continuación se muestran algunas de las preguntas comunes y las áreas de confusión que tiendo a discutir con los clientes.

### <a name="provisioning"></a>Aprovisionamiento

Azure AD no resuelve la falta de gobernanza en el mundo de la identidad. [La gobernanza de identidades](/azure/active-directory/governance/identity-governance-overview) debe ser un elemento crítico independientemente de las decisiones en la nube. Los requisitos de gobernanza cambian con el tiempo, por lo que es un programa y no una herramienta.

[¿Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect) frente [a Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) frente a otra cosa (de terceros o personalizado)? Ahorre mucho dolor de cabeza ahora y en el futuro y vaya con Azure AD Connect. Hay todo tipo de smarts en esta herramienta para abordar configuraciones de clientes peculiares e innovaciones continuas.

Algunos casos perimetrales que pueden conducir hacia una arquitectura más compleja:

- Tengo varios bosques de AD sin conectividad de red entre estos. Hay una nueva opción denominada [Cloud Provisioning](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- No tengo Active Directory ni quiero instalarlo. Azure AD Connect se puede configurar para [la sincronización desde LDAP](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (es posible que se requiera un asociado).
- Necesito aprovisionar los mismos objetos en varios inquilinos. Este escenario no es técnicamente compatible, pero depende de la definición de "igual".

¿Debo personalizar las reglas de sincronización predeterminadas ([objetos de filtro](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [atributos de cambio](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), [identificador de inicio de sesión alternativo](/azure/active-directory/hybrid/plan-connect-userprincipalname), etc.)? ¡Evitarlo! Una plataforma de identidad solo es tan valiosa como los servicios que la usan. Aunque puede realizar todo tipo de configuraciones de nuez, para responder a esta pregunta debe examinar el impacto en las aplicaciones. Si filtra objetos habilitados para correo, la GAL de servicios en línea estará incompleta; si la aplicación se basa en atributos específicos, el filtrado de estos tendrá un impacto imprevisible, etc. No es una decisión del equipo de identidad.

Xyz SaaS admite el aprovisionamiento Just-In-Time (JIT), ¿por qué me requiere sincronizar? Vea lo anterior. Muchas aplicaciones necesitan información de "perfil" para la funcionalidad. No puede tener una GAL si todos los objetos habilitados para correo no están disponibles. Lo mismo se aplica al [aprovisionamiento de usuarios](/azure/active-directory/app-provisioning/user-provisioning) en aplicaciones integradas con Azure AD.

### <a name="authentication"></a>Autenticación

[Sincronización de hash de contraseña](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) frente a [autenticación de paso a través](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) frente a [federación](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Normalmente hay un [debate](/azure/active-directory/hybrid/choose-ad-authn) apasionado en torno a la federación. Lo más sencillo suele ser mejor y, por lo tanto, usar PHS a menos que tenga una buena razón para no hacerlo. También es posible configurar diferentes métodos de autenticación para distintos dominios DNS en el mismo inquilino.

Algunos clientes habilitan la federación y PHS principalmente para:

- Opción a [la que volver](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (para la recuperación ante desastres) si el servicio de federación no está disponible.
- Funcionalidades adicionales (por ejemplo, [Azure AD DS](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) y servicios de seguridad (por ejemplo, [credenciales filtradas](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Compatibilidad con servicios de Azure que no entienden la autenticación federada (por ejemplo, [Azure Files](/azure/storage/files/storage-files-active-directory-overview)).

A menudo, recorra a los clientes a través del flujo de autenticación de cliente para aclarar algunas ideas erróneas. El resultado es similar a la imagen siguiente, que no es tan bueno como el proceso interactivo de llegar allí.

![Ejemplo de conversación de pizarra.](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Este tipo de dibujo de pizarra muestra dónde se aplican las directivas de seguridad dentro del flujo de una solicitud de autenticación. En este ejemplo, las directivas aplicadas a través del Servicio de federación de Active Directory (AD FS) se aplican a la primera solicitud de servicio, pero no a las solicitudes de servicio posteriores. Este comportamiento es al menos una razón para mover los controles de seguridad a la nube tanto como sea posible.

Hemos estado persiguiendo el sueño del [inicio de sesión único](/azure/active-directory/manage-apps/what-is-single-sign-on) (SSO) durante el tiempo que puedo recordar. Algunos clientes creen que pueden lograr esto eligiendo el proveedor de federación "correcto". Azure AD puede ayudar significativamente a [habilitar](/azure/active-directory/manage-apps/plan-sso-deployment) las funcionalidades de SSO, pero ningún STS es mágico. Hay demasiados métodos de autenticación "heredados" que todavía se usan para aplicaciones críticas. La ampliación de Azure AD con [soluciones de asociados](/azure/active-directory/saas-apps/tutorial-list) puede abordar muchos de estos escenarios. El inicio de sesión único es una estrategia y un recorrido. No puede llegar allí sin pasar a [los estándares de las aplicaciones](/azure/active-directory/develop/v2-app-types). Relacionado con este artículo es un viaje a la autenticación [sin contraseña](/azure/active-directory/authentication/concept-authentication-passwordless) , que tampoco tiene una respuesta mágica.

[La autenticación multifactor](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) es esencial hoy en día ([aquí](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) para obtener más). Agréguele [análisis de comportamiento de usuario](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) y tiene una solución que evita los ciberataques más comunes. Incluso los servicios de consumidor se están moviendo para requerir MFA. Sin embargo, todavía me encuentro con muchos clientes que no quieren pasar a los enfoques de [autenticación modernos](../enterprise/hybrid-modern-auth-overview.md) . El argumento más importante que escucho es que afectará a los usuarios y a las aplicaciones heredadas. A veces, un buen golpe podría ayudar a los clientes a avanzar: Exchange Online [cambios anunciados](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282). Ahora hay muchos [informes](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) de Azure AD disponibles para ayudar a los clientes con esta transición.

### <a name="authorization"></a>Authorization

Según [Wikipedia](https://en.wikipedia.org/wiki/Authorization), "autorizar" es definir una directiva de acceso. Muchas personas lo ven como la capacidad de definir controles de acceso a un objeto (archivo, servicio, etc.). En el mundo actual de las ciberamenazas, este concepto evoluciona rápidamente a una directiva dinámica que puede reaccionar ante varios vectores de amenazas y ajustar rápidamente los controles de acceso en respuesta a estos. Por ejemplo, si accedo a mi cuenta bancaria desde una ubicación inusual, obtengo pasos de confirmación adicionales. Para abordar esto, debemos tener en cuenta no solo la propia directiva, sino también el ecosistema de metodologías de detección de amenazas y correlación de señales.

El motor de directivas de Azure AD se implementa mediante [directivas de acceso condicional](/azure/active-directory/conditional-access/overview). Este sistema depende de la información de una variedad de otros sistemas de detección de amenazas para tomar decisiones dinámicas. Una vista sencilla sería algo parecido a la siguiente ilustración:

![Motor de directivas en Azure AD.](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

La combinación de todas estas señales permite directivas dinámicas como estas:

- Si se detecta una amenaza en el dispositivo, el acceso a los datos se reducirá a la web solo sin la capacidad de descarga.
- Si está descargando un volumen inusualmente alto de datos, cualquier cosa que descargue se cifrará y restringirá.
- Si accede a un servicio desde un dispositivo no administrado, se le bloqueará la información altamente confidencial, pero se le permitirá acceder a datos no restringidos sin la capacidad de copiarlos en otra ubicación.

Si está de acuerdo con esta definición ampliada de autorización, debe implementar soluciones adicionales. Las soluciones que implemente dependerán de la dinámica que quiera que sea la directiva y de las amenazas que quiera priorizar. Algunos ejemplos de estos sistemas son:

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/)
- [Microsoft Defender for Identity](/azure-advanced-threat-protection/)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/) (Defender for Cloud Apps)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Purview Information Protection](../compliance/information-protection.md)
- [Microsoft Sentinel](/azure/sentinel/)

Por supuesto, además de Azure AD, varios servicios y aplicaciones tienen sus propios modelos de autorización específicos. Algunas de ellas se describen más adelante en la sección de delegación.

### <a name="audit"></a>Auditoría

Azure AD tiene funcionalidades detalladas [de auditoría e informes](/azure/active-directory/reports-monitoring/) . Sin embargo, estos informes no suelen ser la única fuente de información necesaria para tomar decisiones de seguridad. Consulte más información al respecto en la sección delegación.

## <a name="theres-no-exchange"></a>No hay ningún intercambio

¡No te asustes! Esto no significa que Exchange esté en desuso (o SharePoint, etc.). Sigue siendo un servicio básico. Lo que quiero decir es que, desde hace bastante tiempo, los proveedores de tecnología han estado realizando la transición de experiencias de usuario (UX) para abarcar componentes de varios servicios. En Microsoft 365, un ejemplo sencillo es "[datos adjuntos modernos](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)" donde los datos adjuntos al correo electrónico se almacenan en SharePoint Online o OneDrive para la Empresa.

![Adjuntar un archivo a un correo electrónico.](../media/solutions-architecture-center/modern-attachments.png)

Al examinar el cliente de Outlook, puede ver muchos servicios que están "conectados" como parte de esta experiencia, no solo Exchange. Esto incluye Azure AD, Microsoft Search, Aplicaciones, Perfil, cumplimiento y grupos de Office 365.

![Interfaz de Outlook con llamadas.](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Obtenga información sobre [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) para obtener una vista previa de las próximas funcionalidades. En versión preliminar ahora, puedo leer y responder a las conversaciones de Teams directamente en Outlook. De hecho, el [cliente de Teams](https://products.office.com/microsoft-teams/download-app) es uno de los ejemplos más destacados de esta estrategia.

En general, es cada vez más difícil trazar una línea clara entre Office 365 y otros servicios en las nubes de Microsoft. Lo veo como una gran ventaja para los clientes, ya que pueden beneficiarse de la innovación total en todo lo que hacemos incluso si usan un componente. Bastante genial y tiene implicaciones de gran alcance para muchos clientes.

Hoy en día, me parece que muchos grupos de TI de clientes están estructurados en torno a "productos". Es lógico para un mundo local, ya que necesita un experto para cada producto específico. Sin embargo, estoy totalmente contento de que no tenga que depurar una base de datos de Active Directory o Exchange nunca más, ya que estos servicios se han movido a la nube. La automatización (qué tipo de nube es) elimina ciertos trabajos manuales repetitivos (mira lo que pasó con las fábricas). Sin embargo, estas tareas se reemplazan por requisitos más complejos para comprender la interacción entre servicios, el impacto, las necesidades empresariales, etc. Si está dispuesto a [aprender](/training/), hay grandes oportunidades habilitadas por la transformación en la nube. Antes de saltar a la tecnología, a menudo hablo con los clientes sobre cómo administrar el cambio en las aptitudes de TI y las estructuras de equipo.

Para todos los fans y desarrolladores de SharePoint, deje de preguntar "¿Cómo puedo hacer XYZ en SharePoint online?" Use [Power Automate](/power-automate/) (o Flow) para el flujo de trabajo, es una plataforma mucho más eficaz. Use [Azure Bot Framework](/azure/bot-service/) para crear una experiencia de usuario mejor para la lista de elementos 500-K. Empiece a usar [Microsoft Graph](https://developer.microsoft.com/graph/) en lugar de CSOM. [Microsoft Teams](/MicrosoftTeams/Teams-overview) incluye SharePoint, pero también un mundo más. Hay muchos otros ejemplos que puedo enumerar. Hay un universo vasto y maravilloso ahí fuera. Abra la puerta y [empiece a explorar]().

El otro impacto común es en el área de cumplimiento. Este enfoque entre servicios parece confundir completamente muchas directivas de cumplimiento. Sigo viendo organizaciones que indican: "Tengo que enviar en diario todas las comunicaciones de correo electrónico a un sistema de exhibición de documentos electrónicos". ¿Qué significa esto realmente cuando el correo electrónico ya no es solo correo electrónico, sino una ventana a otros servicios? Office 365 tiene un enfoque integral para [el cumplimiento](../compliance/index.yml), pero los cambios de personas y procesos suelen ser mucho más difíciles que la tecnología.

Hay muchas otras personas y implicaciones en los procesos. En mi opinión, este factor es un área crítica y poco discutida. Quizás más en otro artículo.

## <a name="tenant-structure-options"></a>Opciones de estructura de inquilino

### <a name="single-tenant-vs-multi-tenant"></a>Inquilino único frente a multiinquilino

En general, la mayoría de los clientes solo deben tener un inquilino de producción. Hay muchas razones por las que varios inquilinos son desafiantes (darle una [búsqueda de Bing](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) o leer esta [notas del producto](https://aka.ms/multi-tenant-user). Al mismo tiempo, muchos clientes empresariales con los que trabajo tienen otro inquilino (pequeño) para el aprendizaje, las pruebas y la experimentación de TI. El acceso entre inquilinos a Azure se facilita con [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/). Office 365 y muchos otros servicios SaaS tienen límites para escenarios entre inquilinos. Hay mucho que tener en cuenta en escenarios [B2B de Azure AD](/azure/active-directory/b2b/what-is-b2b) .

Muchos clientes terminan con varios inquilinos de producción después de una fusión y adquisición (M&A) y quieren consolidarse. Hoy en día, eso no es sencillo y requeriría servicios de consultoría de Microsoft (MCS) o un asociado más software de terceros. Hay un trabajo de ingeniería en curso para abordar varios escenarios con clientes multiinquilino en el futuro.

Algunos clientes optan por ir con más de un inquilino. Esta debe ser una decisión muy cuidadosa y casi siempre motivada por la razón empresarial. Algunos ejemplos incluyen los siguientes motivos:

- Una estructura de empresa de tipo holding en la que no se requiere una colaboración sencilla entre diferentes entidades y hay fuertes necesidades administrativas y de aislamiento.
- Después de una adquisición, se toma una decisión empresarial para mantener separadas dos entidades.
- Simulación del entorno de un cliente que no cambia el entorno de producción del cliente.
- Desarrollo de software para clientes.

En estos escenarios multiinquilino, los clientes a menudo quieren mantener la misma configuración entre inquilinos o informar sobre los cambios y desfases de configuración. Esto suele significar pasar de los cambios manuales a la configuración como código. El soporte técnico de Microsoft Premiere ofrece un taller para estos tipos de requisitos basados en esta dirección IP pública: <https://Microsoft365dsc.com>.

### <a name="multi-geo"></a>Multi-Geo

A [multigeográfica](../enterprise/microsoft-365-multi-geo.md) o no a multigeográfica, esa es la pregunta. Con Office 365 multigeográfica, puede aprovisionar y almacenar datos en reposo en las ubicaciones geográficas que ha elegido para cumplir los requisitos [de residencia de datos](../enterprise/o365-data-locations.md). Hay muchos conceptos erróneos sobre esta funcionalidad. Tenga en cuenta lo siguiente:

- No proporciona ventajas de rendimiento. Podría empeorar el rendimiento si el [diseño de red](https://aka.ms/office365networking) no es correcto. Consigue que los dispositivos se "cierren" a la red de Microsoft, no necesariamente a los datos.
- No es una solución para el [cumplimiento del RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-overview). EL RGPD no se centra en la soberanía de los datos ni en las ubicaciones de almacenamiento. Hay otros marcos de cumplimiento para eso.
- No resuelve las barreras de delegación de administración (vea a continuación) ni [de información](../compliance/information-barriers.md).
- No es lo mismo que multiinquilino y requiere flujos de trabajo de [aprovisionamiento de usuarios](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) adicionales.
- No [mueve el inquilino](../enterprise/moving-data-to-new-datacenter-geos.md) (azure AD) a otra geografía.

## <a name="delegation-of-administration"></a>Delegación de administración

En la mayoría de las organizaciones grandes, la separación de tareas y el control de acceso basado en roles (RBAC) es una realidad necesaria. Voy a disculparme antes de tiempo. Esta actividad no es tan sencilla como algunos clientes quieren que sea. Los requisitos de cliente, legal, cumplimiento y otros son diferentes y a veces conflictivos en todo el mundo. La simplicidad y la flexibilidad suelen estar en lados opuestos entre sí. No me malinterpretes, podemos hacer un mejor trabajo en esto. Ha habido (y habrá) mejoras significativas a lo largo del tiempo. Visite el [Centro de tecnología de Microsoft](https://www.microsoft.com/mtc) local para averiguar el modelo que se ajusta a sus requisitos empresariales sin leer los documentos de 379230. Aquí, me centraré en lo que deberías pensar y no en por qué es así. A continuación se muestran cinco áreas diferentes para planear y algunas de las preguntas comunes que he encontrado.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Centros de administración de Azure AD y Microsoft 365

Hay una larga y creciente lista de [roles integrados](/azure/active-directory/roles/permissions-reference). Cada rol consta de una lista de permisos de rol agrupados para permitir que se realicen acciones específicas. Puede ver estos permisos en la pestaña "Descripción" dentro de cada rol. Como alternativa, puede ver una versión más legible de estos permisos en el Centro de Administración de Microsoft 365. No se pueden modificar las definiciones de roles integrados. Por lo general, agrupo estos roles en tres categorías:

- **Administrador global**: este rol "todo eficaz" debe estar [muy protegido](../enterprise/protect-your-global-administrator-accounts.md) como lo haría en otros sistemas. Las recomendaciones típicas incluyen: sin asignación permanente y uso de azure AD Privileged Identity Management (PIM), autenticación segura, etc. Curiosamente, este rol no le da acceso a todo de forma predeterminada. Normalmente, veo confusión sobre el acceso de cumplimiento y el acceso a Azure, que se describen más adelante. Sin embargo, este rol siempre puede asignar acceso a otros servicios del inquilino.
- **Administradores de servicios específicos**: algunos servicios (Exchange, SharePoint, Power BI, etc.) consumen roles de administración de alto nivel de Azure AD. Este comportamiento no es coherente en todos los servicios y hay más roles específicos del servicio que se tratarán más adelante.
- **Funcional**: hay una larga (y creciente) lista de roles centrados en operaciones específicas (invitador, etc.). Periódicamente, se agregan más roles en función de las necesidades del cliente.

No es posible delegar todo (aunque la brecha está disminuyendo), lo que significa que el rol de administrador global tendría que usarse a veces. La configuración como código y la automatización deben tenerse en cuenta en lugar de la pertenencia de personas a este rol.

**Nota**: El Centro de administración de Microsoft 365 tiene una interfaz más fácil de usar, pero tiene un subconjunto de funcionalidades en comparación con la experiencia de administrador de Azure AD. Ambos portales usan los mismos roles de Azure AD, por lo que los cambios se producen en el mismo lugar. Sugerencia: si quiere una interfaz de usuario de administración centrada en la administración de identidades sin todo el desorden de Azure, use <https://aad.portal.azure.com>.

¿Qué hay en el nombre? No realice suposiciones a partir del nombre del rol. El lenguaje no es una herramienta muy precisa. El objetivo debe ser definir las operaciones que deben delegarse antes de examinar qué roles se necesitan. Agregar a alguien al rol "Lector de seguridad" no hace que vea la configuración de seguridad en todo.

La capacidad de crear [roles personalizados](/azure/active-directory/users-groups-roles/roles-custom-overview) es una pregunta común. Esta funcionalidad está limitada en Azure AD hoy en día (consulte a continuación), pero aumentará en capacidades con el tiempo. Pienso en estos roles personalizados como aplicables a las funciones de Azure AD y es posible que no abarque "hacia abajo" el modelo de jerarquía (descrito anteriormente). Cada vez que trato con la "costumbre", tiendo a volver a mi principal de "simple es mejor".

Otra pregunta común es la capacidad de limitar los roles a un subconjunto de un directorio. Un ejemplo es algo parecido a "Administrador del departamento de soporte técnico solo para usuarios de la UE". [Las unidades administrativas](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) están diseñadas para abordar esto. Como en el caso anterior, considero que estos ámbitos son aplicables a las funciones de Azure AD y es posible que no se extiendan "hacia abajo". Por supuesto, ciertos roles no tienen sentido para el ámbito (administradores globales, administradores de servicios, etc.).

En la actualidad, todos estos roles requieren pertenencia directa (o asignación dinámica si usa [PIM de Azure AD](/azure/active-directory/privileged-identity-management/)). Esto significa que los clientes deben administrarlos directamente en Azure AD y estos roles no se pueden basar en una pertenencia a grupos de seguridad. No soy un fan de la creación de scripts para administrar estos roles, ya que tendría que ejecutarse con derechos elevados. Por lo general, recomiendo la integración de API con sistemas de procesos como ServiceNow o el uso de herramientas de gobernanza de asociados como Saviynt. Hay un trabajo de ingeniería que se va solucionando con el tiempo.

He mencionado [PIM de Azure AD](/azure/active-directory/privileged-identity-management/) varias veces. Hay una solución [Privileged Access Management](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) de Microsoft Identity Manager (MIM) correspondiente para controles locales. Es posible que también quiera consultar las estaciones de trabajo de [acceso con privilegios](/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW) y [la gobernanza de identidades de Azure AD](/azure/active-directory/governance/identity-governance-overview). También hay varias herramientas de terceros, que pueden habilitar la elevación de roles just-in-time, just-enough y dynamic. Esta funcionalidad suele formar parte de una discusión más amplia para proteger un entorno.

En ocasiones, los escenarios llaman a agregar un usuario externo a un rol (consulte la sección multiinquilino anterior). Esto funciona bien. [Azure AD B2B](/azure/active-directory/b2b/) es otro artículo grande y divertido para guiar a los clientes, quizás en otro artículo.

### <a name="microsoft-365-defender-and-microsoft-365-purview-compliance-portals"></a>portales de cumplimiento de Microsoft 365 Defender y Microsoft 365 Purview

**Email & Roles de colaboración** en el [portal de Microsoft 365 Defender](../security/office-365-security/permissions-microsoft-365-security-center.md) y **_Grupos de roles para soluciones de Microsoft Purview_* en el portal de [cumplimiento de Microsoft 365 Purview](../compliance/microsoft-365-compliance-center-permissions.md) son una colección de "grupos de roles", que son independientes y distintos de los roles de Azure AD. Esto puede resultar confuso porque algunos de estos grupos de roles tienen el mismo nombre que los roles de Azure AD (por ejemplo, Lector de seguridad), pero pueden tener una pertenencia diferente. Prefiero el uso de roles de Azure AD. Cada grupo de roles consta de uno o varios "roles" (vea lo que quiero decir sobre la reutilización de la misma palabra) y tiene miembros de Azure AD, que son objetos habilitados para correo electrónico. Además, puede crear un grupo de roles con el mismo nombre que un rol, que puede contener o no ese rol (evite esta confusión).

En un sentido, estos permisos son una evolución del modelo de grupos de roles de Exchange. Sin embargo, Exchange Online tiene su propia interfaz [de administración de grupos de roles](/exchange/permissions-exo). Algunos grupos de roles de Exchange Online se bloquean y administran desde Azure AD o los portales de cumplimiento de Microsoft 365 Defender y Microsoft 365 Purview, pero otros pueden tener los mismos nombres o similares y se administran en Exchange Online (lo que agrega confusión). Le recomiendo que evite usar la interfaz de usuario Exchange Online a menos que necesite ámbitos para la administración de Exchange.

No puede crear roles personalizados. Los roles se definen mediante los servicios creados por Microsoft y crecerán a medida que se introduzcan nuevos servicios. Este comportamiento es similar en concepto a [los roles definidos por las aplicaciones](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) en Azure AD. Cuando se habilitan nuevos servicios, a menudo es necesario crear nuevos grupos de roles para conceder o delegar el acceso a estos (por ejemplo, [la administración de riesgos internos](../compliance/insider-risk-management-configure.md)).

Estos grupos de roles también requieren pertenencia directa y no pueden contener grupos de Azure AD. Desafortunadamente, hoy en día estos grupos de roles no son compatibles con PIM de Azure AD. Al igual que los roles de Azure AD, tiendo a recomendar la administración de estos grupos de roles a través de API o un producto de gobernanza de asociados como Saviynt u otros.

Microsoft 365 Defender portal y los roles del portal de cumplimiento de Microsoft 365 Purview abarcan Microsoft 365 y no puede limitar estos grupos de roles a un subconjunto del entorno (como puede hacer con las unidades administrativas de Azure AD). Muchos clientes preguntan cómo pueden subdelegar. Por ejemplo, "cree una directiva DLP solo para usuarios de la UE". En la actualidad, si tiene derechos sobre una función específica en los portales de cumplimiento de Microsoft 365 Defender y Microsoft 365 Purview, tiene derechos sobre todo lo que cubre esta función en el inquilino. Sin embargo, muchas directivas tienen capacidades para dirigirse a un subconjunto del entorno (por ejemplo, "hacer que estas [etiquetas](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) solo estén disponibles para estos usuarios"). La gobernanza y la comunicación adecuadas son un componente clave para evitar conflictos. Algunos clientes optan por implementar un enfoque de "configuración como código" para abordar la subdelegación en los portales de cumplimiento de Microsoft 365 Defender y Microsoft 365 Purview. Algunos servicios específicos admiten la subdelegación (consulte a continuación).

### <a name="service-specific"></a>Específico del servicio

Como se indicó anteriormente, muchos clientes buscan lograr un modelo de delegación más granular. Un ejemplo común: "Administrar el servicio XYZ solo para usuarios y ubicaciones de división X" (u otra dimensión). La capacidad de hacerlo depende de cada servicio y no es coherente entre servicios y funcionalidades. Además, cada servicio puede tener un modelo de RBAC independiente y único. En lugar de analizar todos estos modelos (tardará para siempre), voy a agregar vínculos pertinentes para cada servicio. Esta lista no está completa, pero le ayudará a empezar.

- **Exchange Online**: (/exchange/permissions-exo/permissions-exo)
- **SharePoint Online** : (/sharepoint/manage-site-collection-administrators)
- **Microsoft Teams** : (/microsoftteams/itadmin-readiness)
- **eDiscovery** : (.. /compliance/index.yml)
  - **Filtrado de permisos** : (.. /compliance/index.yml)
  - **Límites de cumplimiento** : (.. /compliance/set-up-compliance-boundaries.md)
  - **eDiscovery (Premium):** (.. /compliance/overview-ediscovery-20.md)
- **Yammer** : (/yammer/manage-yammer-users/manage-yammer-admins)
- **Multigeográfica:** (.. /enterprise/add-a-sharepoint-geo-admin.md)
- **Dynamics 365** : (/dynamics365/)

  Nota: Este vínculo se encuentra en la raíz de la documentación. Hay varios tipos de servicios con variaciones en el modelo de administración y delegación.

- **Power Platform** : (/power-platform/admin/admin-documentation)
  - **Power Apps** : (/power-platform/admin/wp-security)

    Nota: hay varios tipos con variaciones en los modelos de administración y delegación.

  - **Power Automate** : (/power-automate/environments-overview-admin)
  - **Power BI** : (/power-bi/service-admin-governance)

    Nota: La seguridad y delegación de la plataforma de datos (que Power BI es un componente) es un área compleja.

- **MEM/Intune**: (/mem/intune/fundamentals/role-based-access-control)
- **Microsoft Defender para punto de conexión**: (/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - (.. /security/defender/m365d-permissions.md)
- **Microsoft Defender for Cloud Apps**: (/cloud-app-security/manage-admins)
- **Stream** : (/stream/assign-administrator-user-role)
- **Barreras de información** : (.. /compliance/information-barriers.md)

### <a name="activity-logs"></a>Registros de actividad

Office 365 tiene un [registro de auditoría unificado](../compliance/search-the-audit-log-in-security-and-compliance.md). Es un [registro muy detallado](/office/office-365-management-api/office-365-management-activity-api-schema), pero no leas demasiado en el nombre. Es posible que no contenga todo lo que quiera o necesite para sus necesidades de seguridad y cumplimiento. Además, algunos clientes están realmente interesados en [Audit (Premium)](../compliance/advanced-audit.md).

Entre los ejemplos de registros de Microsoft 365 a los que se accede a través de otras API se incluyen las siguientes características:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (actividades no relacionadas con Office 365)
- [Seguimiento de mensajes de Exchange](/powershell/module/exchange/get-messagetrace)
- Sistemas de Amenaza/UEBA descritos anteriormente (por ejemplo, Azure AD Identity Protection, Microsoft Defender for Cloud Apps, Microsoft Defender para punto de conexión, etc.)
- [Microsoft Purview Information Protection](../compliance/data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Es importante identificar primero todos los orígenes de registro necesarios para un programa de seguridad y cumplimiento. Tenga en cuenta también que los distintos registros tienen distintos límites de retención en línea.

Desde la perspectiva de la delegación de administración, la mayoría de los registros de actividad de Microsoft 365 no tienen un modelo RBAC integrado. Si tiene permiso para ver un registro, puede ver todo en él. Un ejemplo común de un requisito de cliente es: "Quiero poder consultar la actividad solo para los usuarios de la UE" (u otra dimensión). Para lograr este requisito, es necesario transferir los registros a otro servicio. En la nube de Microsoft, se recomienda transferirlo a [Microsoft Sentinel](/azure/sentinel/overview) o [Log Analytics](/azure/azure-monitor/learn/quick-create-workspace).

Diagrama de alto nivel:

![diagrama de orígenes de registro para un programa de seguridad y cumplimiento.](../media/solutions-architecture-center/identity-beyond-illustration-4.png)

El diagrama anterior representa funcionalidades integradas para enviar registros al centro de eventos o a Azure Storage o Azure Log Analytics. Todavía no todos los sistemas incluyen este elemento de fábrica. Pero hay otros enfoques para enviar estos registros al mismo repositorio. Por ejemplo, consulte [Protección de Teams con Microsoft Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

La combinación de todos los registros en una ubicación de almacenamiento incluye ventajas adicionales, como correlaciones cruzadas, tiempos de retención personalizados, aumento con los datos necesarios para admitir el modelo RBAC, etc. Una vez que los datos están en este sistema de almacenamiento, puede crear un panel de Power BI (u otro tipo de visualización) con un modelo de RBAC adecuado.

Los registros no tienen que dirigirse a un solo lugar. También puede ser beneficioso integrar [registros de Office 365 con Microsoft Defender for Cloud Apps](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) o un modelo de RBAC personalizado en [Power BI](../admin/usage-analytics/usage-analytics.md). Los distintos repositorios tienen diferentes ventajas y audiencias.

Vale la pena mencionar que hay un sistema de análisis integrado muy completo para seguridad, amenazas, vulnerabilidades, etc. en un servicio denominado [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md).

Muchos clientes grandes quieren transferir estos datos de registro a un sistema de terceros (por ejemplo, SIEM). Hay diferentes enfoques para esto, pero en general [, Azure Event Hub](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) y [Graph](/graph/security-integration) son buenos puntos de partida.

### <a name="azure"></a>Azure

A menudo se me pregunta si hay una manera de separar roles con privilegios elevados entre Azure AD, Azure y SaaS (por ejemplo, administrador global para Office 365 pero no Azure). La verdad es que no. La arquitectura multiinquilino es necesaria si se requiere una separación administrativa completa, pero esto agrega [una complejidad](https://aka.ms/multi-tenant-user) significativa (consulte anteriormente). Todos estos servicios forman parte del mismo límite de seguridad e identidad (observe el modelo de jerarquía anterior).

Es importante comprender las relaciones entre varios servicios del mismo inquilino. Trabajo con muchos clientes que crean soluciones empresariales que abarcan Azure, Office 365 y Power Platform (y, a menudo, también servicios en la nube locales y de terceros). Un ejemplo común:

1. Quiero colaborar en un conjunto de documentos, imágenes, etc. (Office 365)
2. Enviar cada uno de ellos a través de un proceso de aprobación (Power Platform)
3. Una vez aprobados todos los componentes, ensambla estos elementos en una entrega unificada (Azure) [de Microsoft Graph API](/azure/active-directory/develop/microsoft-graph-intro) es tu mejor amigo aquí. No es imposible, pero es mucho más complejo diseñar una solución que abarque [varios inquilinos](/azure/active-directory/develop/single-and-multi-tenant-apps).

Azure Role-Based Access Control (RBAC) permite una administración de acceso específica para Azure. Con RBAC, puede administrar el acceso a los recursos al conceder a los usuarios los permisos más mínimos necesarios para realizar sus trabajos. Los detalles están fuera del ámbito de este documento, pero para obtener más información sobre RBAC, consulte [¿Qué es el control de acceso basado en rol (RBAC) en Azure?](/azure/role-based-access-control/overview) RBAC es importante, pero solo una parte de las consideraciones de gobernanza de Azure. [Cloud Adoption Framework](/azure/cloud-adoption-framework/govern/) es un excelente punto de partida para obtener más información. Me gusta cómo mi amigo [, Andres Ravinet](https://www.linkedin.com/in/andres-ravinet/), guía a los clientes paso a paso a través de varios componentes para decidir sobre el enfoque. La vista de alto nivel de varios elementos (no tan buena como el proceso para llegar al modelo de cliente real) es similar a esta:

![Vista de alto nivel de los componentes de Azure para la administración delegada.](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Como puede ver en la imagen anterior, muchos otros servicios deben considerarse como parte del diseño (por ejemplo, [Directivas de Azure](/azure/governance/policy/overview), [Azure Blueprints](/azure/governance/blueprints/overview), [Grupos de administración](/azure/governance/management-groups/), etc.).

## <a name="conclusion"></a>Conclusión

Comenzó como un breve resumen, terminó más de lo esperado. Espero que ahora esté listo para aventurarse en una profunda visualización de la creación del modelo de delegación para su organización. Esta conversación es muy común con los clientes. No hay ningún modelo que funcione para todos. Esperando algunas mejoras planeadas de la ingeniería de Microsoft antes de documentar patrones comunes que vemos entre los clientes. Mientras tanto, puede trabajar con el equipo de su cuenta Microsoft para organizar una visita al [Centro de tecnología de Microsoft](https://www.microsoft.com/mtc) más cercano. ¡Nos vemos allí!
