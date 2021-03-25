---
title: 'Planeación de recursos empresariales de Microsoft 365: arquitectura de seguridad'
description: Obtenga información sobre las principales estrategias de diseño para la arquitectura de Microsoft Enterprise de Alex Shteynberg, arquitecto principal técnico de Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: da70bbfe5c4dfa4f9eda16adec709826de1247b7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200022"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Para identidad y más allá: un punto de vista de un arquitecto

En este artículo, [Alex Shteynberg,](https://www.linkedin.com/in/alex-shteynberg/)arquitecto técnico principal de Microsoft, analiza las principales estrategias de diseño para las organizaciones empresariales que adoptan Microsoft 365 y otros servicios en la nube de Microsoft.

## <a name="about-the-author"></a>Acerca del autor

![Foto de Alex Shteynberg](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Soy arquitecto técnico principal en el Centro de tecnología [de Microsoft de Nueva](https://www.microsoft.com/mtc?rtc=1)York. Trabajo principalmente con clientes grandes y requisitos complejos. Mi punto de vista y opiniones se basan en estas interacciones y puede que no se apliquen a todas las situaciones. Sin embargo, en mi experiencia, si podemos ayudar a los clientes con los desafíos más complejos, podemos ayudar a todos los clientes.

Normalmente trabajo con más de 100 clientes cada año. Aunque cada organización tiene características únicas, es interesante ver tendencias y aspectos comunes. Por ejemplo, una tendencia es el interés entre sectores para muchos clientes. Después de todo, una sucursal bancaria también puede ser una cafetería y un centro de la comunidad.

En mi rol, me enfoque en ayudar a los clientes a llegar a la mejor solución técnica para abordar su conjunto único de objetivos empresariales. Oficialmente, me foco en Identidad, Seguridad, Privacidad y Cumplimiento. Me encanta el hecho de que estos toquen todo lo que hacemos. Me da la oportunidad de participar en la mayoría de los proyectos. Esto me mantiene bastante ocupado y disfrutando de este rol.

Vivo en la ciudad de Nueva York (¡la mejor!) y realmente me gusta la diversidad de su cultura, comida y personas (no tráfico). Me encanta viajar cuando puedo y espero ver la mayor parte del mundo en mi vida. Actualmente estoy investigando un viaje a África para aprender sobre la vida silvestre.

## <a name="guiding-principles"></a>Principios de guía

- **Simple suele ser mejor:** puedes hacer (casi) cualquier cosa con tecnología, pero no significa que debas hacerlo. Especialmente en el espacio de seguridad, muchos clientes sobreingeniería soluciones. Me gusta [este vídeo de](https://www.youtube.com/watch?v=SOQgABDSYZE) la conferencia Stripe de Google para destacar este punto.
- **Personas, proceso, tecnología:** [diseño para que las personas](https://en.wikipedia.org/wiki/Human-centered_design) mejoren el proceso, no primero la tecnología. No hay soluciones "perfectas". Debemos equilibrar varios factores de riesgo y las decisiones serán diferentes para cada empresa. Demasiados clientes diseñan un enfoque que sus usuarios más adelante evitan.
- **Céntrate en "por qué" primero y "cómo"** más adelante: Sé el molesto niño de 7 años con un millón de preguntas. No podemos llegar a la respuesta correcta si no conocemos las preguntas correctas que hacer. Muchos clientes asumen cómo deben funcionar las cosas en lugar de definir el problema empresarial. Siempre hay varias rutas de acceso que se pueden tomar.
- **Larga cola de procedimientos recomendados pasados:** reconocer que los procedimientos recomendados están cambiando a velocidad de luz. Si ha visto Azure AD hace más de tres meses, es probable que no esté actualizado. Todo aquí está sujeto a cambios después de la publicación. La opción "Mejor" hoy puede no ser la misma de seis meses a partir de ahora.

## <a name="baseline-concepts"></a>Conceptos de línea base

No omita esta sección. A menudo encuentro que debo dar un paso atrás en estos temas, incluso para los clientes que han estado usando servicios en la nube durante años.
Lamentablemente, el idioma no es una herramienta precisa. A menudo usamos la misma palabra para significar conceptos diferentes o palabras diferentes para significar el mismo concepto. A menudo uso este diagrama siguiente para establecer alguna terminología de línea base y "modelo de jerarquía".
<br><br>

![Ilustración de inquilino, suscripción, servicio y datos](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Cuando aprendes a nado, es mejor empezar en la piscina y no en medio del océano. No intento ser técnicamente preciso con este diagrama. Es un modelo para analizar algunos conceptos básicos.

En el diagrama:

- Tenant = una instancia de Azure AD. Está en la "parte superior" de una jerarquía o en el nivel 1 del diagrama. Podemos considerar que este es el["límite"](/azure/active-directory/users-groups-roles/licensing-directory-independence)donde ocurre todo lo demás[(aparte de Azure AD B2B).](/azure/active-directory/b2b/what-is-b2b) Todos los servicios en la nube de microsoft enterprise forman parte de uno de estos inquilinos. Los servicios de consumidor son independientes. "Inquilino" aparece en la documentación como inquilino de Office 365, inquilino de Azure, inquilino de WVD, y así sucesivamente. A menudo encuentro que estas variaciones causan confusión para los clientes.
- Servicios/suscripciones, nivel 2 en el diagrama, pertenecen a un único espacio empresarial. La mayoría de los servicios SaaS son 1:1 y no se pueden mover sin la migración. Azure es diferente, puede mover [la](/azure/cost-management-billing/manage/billing-subscription-transfer) facturación o una [suscripción](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) a otro inquilino. Hay muchos clientes que necesitan mover suscripciones de Azure. Esto tiene varias implicaciones. Los objetos que existen fuera de la suscripción no se mueven (por ejemplo, control de acceso basado en roles o RBAC de Azure y objetos de Azure AD, incluidos grupos, aplicaciones, directivas, entre otros). Además, algunos servicios (como Azure Key Vault, Data Bricks, entre otros). No migre los servicios sin una buena necesidad empresarial. Algunos scripts que pueden ser útiles para la migración [se comparten en GitHub](https://github.com/lwajswaj/azure-tenant-migration).
- Un servicio determinado suele tener algún tipo de límite "subnivel" o nivel 3 (L3). Esto es útil para comprender la segregación de la seguridad, las directivas, el gobierno, y así sucesivamente. Desafortunadamente, no hay ningún nombre uniforme que conozca. Algunos nombres de ejemplo para L3 son: Suscripción de Azure = [recurso;](/azure/azure-resource-manager/management/manage-resources-portal) Dynamics 365 CE = [instancia](/dynamics365/admin/new-instance-management); Power BI = [área de trabajo;](/power-bi/service-create-the-new-workspaces) Power Apps = [entorno](/power-platform/admin/environments-overview); y así sucesivamente.
- El nivel 4 es donde viven los datos reales. Este "plano de datos" es un tema complejo. Algunos servicios usan Azure AD para RBAC, otros no. Lo analizaré un poco cuando lleguemos a temas de delegación.

Algunos conceptos adicionales que encuentro que muchos clientes (y empleados de Microsoft) están confundidos o tienen preguntas sobre:

- Cualquier persona [puede crear](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) muchos inquilinos [sin costo.](https://azure.microsoft.com/pricing/details/active-directory/) No es necesario que se aprovisione un servicio dentro de él. Tengo decenas. Cada nombre de inquilino es único en el servicio en la nube mundial de Microsoft (es decir, no hay dos inquilinos que puedan tener el mismo nombre). Todos tienen el formato de TenantName.onmicrosoft.com. También hay procesos que crean inquilinos automáticamente ([inquilinos no administrados](/azure/active-directory/users-groups-roles/directory-self-service-signup)). Por ejemplo, esto puede ocurrir cuando un usuario se inscribe en un servicio de empresa con un dominio de correo electrónico que no existe en ningún otro espacio empresarial.
- En un inquilino administrado, muchos [dominios DNS](/azure/active-directory/fundamentals/add-custom-domain) se pueden registrar en él. Esto no cambia el nombre del inquilino original. Actualmente no hay una forma fácil de cambiar el nombre de un inquilino (aparte de la migración). Aunque el nombre del inquilino no es técnicamente crítico en estos días, algunos pueden encontrar que esto sea limitante.
- Debe reservar un nombre de inquilino para su organización incluso si aún no está planeando implementar ningún servicio. De lo contrario, alguien puede quitarlo y no hay ningún proceso sencillo para recuperarlo (mismo problema que los nombres DNS). Oigo esto con demasiada frecuencia por parte de los clientes. El nombre del inquilino también debe ser un tema de debate.
- Si es propietario de espacios de nombres DNS, debe agregarlos todos a los inquilinos. De lo contrario, se podría crear [un](/azure/active-directory/users-groups-roles/directory-self-service-signup) inquilino no administrado con este nombre, lo que, a continuación, provocaría una interrupción [para que se administrara](/azure/active-directory/users-groups-roles/domains-admin-takeover).
- El espacio de nombres DNS (como contoso.com) puede pertenecer a un único inquilino. Esto tiene implicaciones para varios escenarios (por ejemplo, compartir un dominio de correo electrónico durante una fusión o adquisición, y así sucesivamente). Hay una forma de registrar un sub DNS (como div.contoso.com) en un inquilino diferente, pero eso debe evitarse. Al registrar un nombre de dominio de nivel superior, se supone que todos los subdominios pertenecen al mismo inquilino. En escenarios multiinquilino (vea a continuación) normalmente se recomienda usar otro nombre de dominio de nivel superior (como contoso.ch o ch-contoso.com).
- ¿Quién debe ser "propietario" de un inquilino? A menudo veo clientes que no saben quién es propietario actualmente de su inquilino. Esta es una gran marca roja. Llame al soporte técnico de Microsoft lo antes posible. Igual de problemático es cuando un propietario del servicio (a menudo un administrador de Exchange) se designa para administrar un inquilino. El espacio empresarial contendrá todos los servicios que desee en el futuro. El propietario del espacio empresarial debe ser un grupo que pueda tomar decisiones para habilitar todos los servicios en la nube de una organización. Otro problema es cuando se pide a un grupo de propietarios del espacio empresarial que administre todos los servicios. Esto no escala para organizaciones grandes.
- No hay ningún concepto de inquilino sub/super. Por alguna razón, este mito se repite a sí mismo. Esto también se aplica a los inquilinos [de Azure AD B2C.](/azure/active-directory-b2c/) Oigo demasiadas veces: "Mi entorno B2C está en mi inquilino XYZ" o "¿Cómo puedo mover mi inquilino de Azure a mi inquilino de Office 365?"
- Este documento se centra principalmente en la nube comercial mundial, ya que esto es lo que usan la mayoría de los clientes. A veces resulta útil conocer las [nubes soberanas](/azure/active-directory/develop/authentication-national-cloud). Las nubes soberanas tienen implicaciones adicionales para analizar cuáles están fuera del ámbito de esta discusión.

## <a name="baseline-identity-topics"></a>Temas de identidad de línea base

Hay mucha documentación sobre la plataforma de identidad de Microsoft: Azure Active Directory (Azure AD). Para los que están empezando, a menudo resulta abrumador. Incluso después de conocerlo, mantenerse al día con la innovación y el cambio constantes puede ser un desafío. En las interacciones de mis clientes, a menudo me encuentro como "traductor" entre los objetivos empresariales y los enfoques "Bueno, Mejor, Mejor" para abordar estos (y las "notas de precipicio" humanas para estos temas). Rara vez hay una respuesta perfecta y la decisión "correcta" es un equilibrio de varios factores de riesgo. A continuación se muestran algunas de las preguntas y áreas de confusión comunes que suelo tratar con los clientes.

### <a name="provisioning"></a>Aprovisionamiento

Azure AD no resuelve la falta de gobierno en el mundo de la identidad. [El gobierno de](/azure/active-directory/governance/identity-governance-overview) identidades debe ser un elemento crítico independiente de las decisiones en la nube. Los requisitos de gobierno cambian con el tiempo, por lo que es un programa y no una herramienta.

[Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect) frente a [Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) frente a otra cosa (de terceros o personalizado)? Ahorre mucho dolor de cabeza ahora y en el futuro e vaya con Azure AD Connect. Hay todo tipo de smarts en esta herramienta para abordar configuraciones de clientes peculiares e innovaciones continuas.

Algunos casos perimetrales que pueden conducir hacia una arquitectura más compleja:

- Tengo varios bosques de AD sin conectividad de red entre estos. Hay una nueva opción denominada [Aprovisionamiento en la nube.](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- No tengo Active Directory ni quiero instalarlo. Azure AD Connect se puede configurar para que [se sincronice desde LDAP](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (es posible que sea necesario un partner).
- Necesito aprovisionar los mismos objetos a varios inquilinos. No se admite técnicamente, pero depende de la definición de "igual".

¿Debo personalizar las reglas de sincronización predeterminadas[(objetos de filtro,](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [atributos de](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)cambio, identificador de [inicio](/azure/active-directory/hybrid/plan-connect-userprincipalname)de sesión alternativo, y así sucesivamente)? Evitarlo. Una plataforma de identidad es tan valiosa como los servicios que la usan. Aunque puede hacer todo tipo de configuraciones de nuez, para responder a esta pregunta necesita ver el impacto en las aplicaciones. Si filtra objetos habilitados para correo, la GAL de los servicios en línea estará incompleta; si la aplicación se basa en atributos específicos, el filtrado de estos tendrá un impacto impredecible; y así sucesivamente. No es una decisión de equipo de identidad.

Xyz SaaS admite el aprovisionamiento just-in-time (JIT), ¿por qué me necesita sincronizar? Vea arriba. Muchas aplicaciones necesitan información de "perfil" para la funcionalidad. No puede tener una GAL si todos los objetos habilitados para correo no están disponibles. Lo mismo se aplica al [aprovisionamiento de](/azure/active-directory/app-provisioning/user-provisioning) usuarios en aplicaciones integradas con Azure AD.

### <a name="authentication"></a>Autenticación

[Sincronización de hash de contraseña](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) frente a autenticación de paso a [través](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) frente a [federación](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Por lo general, hay un [debate apasionado en](/azure/active-directory/hybrid/choose-ad-authn) torno a la federación. Lo más sencillo suele ser mejor y, por lo tanto, usar PHS a menos que tenga una buena razón para no hacerlo. También es posible configurar distintos métodos de autenticación para distintos dominios DNS en el mismo inquilino. 

Algunos clientes habilitan la federación + PHS principalmente para:

- Una opción para [volver a](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (para la recuperación ante desastres) si el servicio de federación no está disponible.
- Capacidades adicionales (por ejemplo: [Azure AD DS](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) y servicios de seguridad (por ejemplo: [credenciales filtradas](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Compatibilidad con servicios de Azure que no comprenden la autenticación federada (por ejemplo, [Azure Files](/azure/storage/files/storage-files-active-directory-overview)).

A menudo, paso a los clientes por el flujo de autenticación de cliente para aclarar algunos conceptos erróneos. El resultado es similar a la imagen siguiente, que no es tan bueno como el proceso interactivo de llegar allí.

![Conversación de pizarra de ejemplo](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Este tipo de dibujo de pizarra ilustra dónde se aplican directivas de seguridad dentro del flujo de una solicitud de autenticación. En este ejemplo, las directivas aplicadas a través del servicio de federación de Active Directory (AD FS) se aplican a la primera solicitud de servicio, pero no a las solicitudes de servicio posteriores. Este es al menos un motivo para mover los controles de seguridad a la nube tanto como sea posible.

Llevamos buscando el sueño del [inicio](/azure/active-directory/manage-apps/what-is-single-sign-on) de sesión único (SSO) durante el tiempo que pueda recordar. Algunos clientes creen que pueden lograrlo eligiendo el proveedor de federación "correcto" (STS). Azure AD puede ayudar significativamente a habilitar [las funcionalidades](/azure/active-directory/manage-apps/plan-sso-deployment) de SSO, pero ningún STS es mágico. Hay demasiados métodos de autenticación "heredados" que todavía se usan para aplicaciones críticas. La extensión de Azure AD con soluciones [de partners](/azure/active-directory/saas-apps/tutorial-list) puede solucionar muchos de estos escenarios. SSO es una estrategia y un recorrido. No se puede llegar sin avanzar hacia los [estándares de las aplicaciones](/azure/active-directory/develop/v2-app-types). Relacionado con este tema es un viaje a la autenticación [sin](/azure/active-directory/authentication/concept-authentication-passwordless) contraseña, que tampoco tiene una respuesta mágica.

[La autenticación multifactor](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) es esencial hoy en[día (aquí](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) para obtener más información). Agrega análisis de [comportamiento de usuario](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) y tienes una solución que evita los ataques cibernéticos más comunes. Incluso los servicios de consumidores se mueven para requerir MFA. Sin embargo, aún me encuentro con muchos clientes que no desean pasar a los [enfoques de autenticación](../enterprise/hybrid-modern-auth-overview.md) modernos. El argumento más importante que oigo es que afectará a los usuarios y las aplicaciones heredadas. A veces, un buen resultado puede ayudar a los clientes a seguir adelante: Exchange Online [anunció cambios](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282). Ahora hay muchos informes [de](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) Azure AD disponibles para ayudar a los clientes con esta transición.

### <a name="authorization"></a>Authorization

Por [Wikipedia,](https://en.wikipedia.org/wiki/Authorization)"autorizar" es definir una directiva de acceso. Muchas personas lo ven como la capacidad de definir controles de acceso a un objeto (archivo, servicio, entre otros). En el mundo actual de las amenazas cibernéticas, este concepto está evolucionando rápidamente a una directiva dinámica que puede reaccionar a varios vectores de amenazas y ajustar rápidamente los controles de acceso en respuesta a estas. Por ejemplo, si tengo acceso a mi cuenta bancaria desde una ubicación inusual, recibiré pasos de confirmación adicionales. Para abordar esto, debemos considerar no solo la directiva en sí, sino el ecosistema de metodologías de detección de amenazas y correlación de señales.

El motor de directivas de Azure AD se implementa mediante directivas [de acceso condicional.](/azure/active-directory/conditional-access/overview) Este sistema depende de la información de una variedad de otros sistemas de detección de amenazas para tomar decisiones dinámicas. Una vista sencilla sería algo parecido a la siguiente ilustración:

![Motor de directivas en Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

La combinación de todas estas señales permite directivas dinámicas como estas:

- Si se detecta una amenaza en el dispositivo, el acceso a los datos solo se reducirá a la web sin la capacidad de descarga.
- Si está descargando un volumen de datos inusualmente alto, todo lo que descargue se cifrará y restringirá.
- Si accedes a un servicio desde un dispositivo no administrado, se te bloquearán los datos altamente confidenciales, pero se te permitirá acceder a datos no restringidos sin la posibilidad de copiarlo en otra ubicación.

Si está de acuerdo con esta definición expandida de autorización, debe implementar soluciones adicionales. Las soluciones que implemente dependerán de la dinámica que desee que sea la directiva y de las amenazas que desee priorizar. Algunos ejemplos de estos sistemas son:

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/) 
- [Microsoft Defender for Identity](/azure-advanced-threat-protection/)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md?view=o365-worldwide)
- [Microsoft Cloud App Security](/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md?view=o365-worldwide)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Information Protection](../compliance/information-protection.md?view=o365-worldwide) (MIP)
- [Azure Sentinel](/azure/sentinel/)

Por supuesto, además de Azure AD, varios servicios y aplicaciones tienen sus propios modelos de autorización específicos. Algunos de estos temas se analizan más adelante en la sección de delegación.

### <a name="audit"></a>Auditoría

Azure AD tiene funciones detalladas [de auditoría e informes.](/azure/active-directory/reports-monitoring/) Sin embargo, esta no suele ser la única fuente de información necesaria para tomar decisiones de seguridad. Vea más información al respecto en la sección de delegación.

## <a name="theres-no-exchange"></a>No hay Exchange

No entres en pánico. Esto no significa que Exchange esté en desuso (o SharePoint, y así sucesivamente). Sigue siendo un servicio básico. Lo que quiero decir es que, desde hace bastante tiempo, los proveedores de tecnología han estado transfiriendo experiencias de usuario (UX) para abarcar componentes de varios servicios. En Microsoft 365, un ejemplo sencillo es["datos](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)adjuntos modernos" donde los datos adjuntos al correo electrónico se almacenan en SharePoint Online o OneDrive para la Empresa.

![Adjuntar un archivo a un correo electrónico](../media/solutions-architecture-center/modern-attachments.png)

Si observa el cliente de Outlook, puede ver muchos servicios que están "conectados" como parte de esta experiencia, no solo Exchange. Esto incluye Azure AD, Microsoft Search, Aplicaciones, Perfil, cumplimiento y grupos de Office 365. 

![Interfaz de Outlook con llamadas](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Lea acerca [de Microsoft Fluid Framework para](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) obtener una vista previa de las próximas funcionalidades. En vista previa ahora, puedo leer y responder a las conversaciones de Teams directamente en Outlook. De hecho, el [cliente de Teams](https://products.office.com/microsoft-teams/download-app) es uno de los ejemplos más destacados de esta estrategia. 

En general, es cada vez más difícil dibujar una línea clara entre Office 365 y otros servicios en las nubes de Microsoft. Lo veo como una gran ventaja para los clientes, ya que pueden beneficiarse de la innovación total en todo lo que hacemos, incluso si usan un componente. Bastante interesante y tiene implicaciones de gran alcance para muchos clientes.

Hoy en día, me parece que muchos grupos de IT de clientes están estructurados en torno a "productos". Es lógico para un mundo local, ya que necesita un experto para cada producto específico. Sin embargo, estoy totalmente contento de que no tenga que volver a depurar una base de datos de Active Directory o Exchange cuando estos servicios se han movido a la nube. La automatización (que es el tipo de nube) quita ciertos trabajos manuales repetitivos (mira lo que sucedió con las fábricas). Sin embargo, se reemplazan por requisitos más complejos para comprender la interacción entre servicios, el impacto, las necesidades empresariales, etc. Si está dispuesto a [aprender,](/learn/)hay grandes oportunidades habilitadas por la transformación en la nube. Antes de saltar a la tecnología, a menudo conversa con los clientes sobre cómo administrar los cambios en las habilidades de TI y las estructuras de equipo.

Para todos los usuarios y desarrolladores de SharePoint, deje de preguntar "¿Cómo puedo hacer XYZ en SharePoint online?" Use [Power Automate](/power-automate/) (o Flow) para el flujo de trabajo, es una plataforma mucho más eficaz. Use [Azure Bot Framework](/azure/bot-service/?view=azure-bot-service-4.0) para crear una experiencia de usuario mejor para la lista de elementos de 500 K. Comience a usar [Microsoft Graph en](https://developer.microsoft.com/graph/) lugar de CSOM. [Microsoft Teams](/MicrosoftTeams/Teams-overview) incluye SharePoint, pero también un mundo más. Hay muchos otros ejemplos que puedo enumerar. Hay un vasto y maravilloso universo por ahí. Abra la puerta y [comience a explorar]().

El otro impacto común está en el área de cumplimiento. Este enfoque entre servicios parece confundir completamente muchas directivas de cumplimiento. Sigo viendo a las organizaciones que den el estado: "Necesito realizar un registro en diario de todas las comunicaciones de correo electrónico a un sistema de exhibición de documentos electrónicos". ¿Qué significa esto realmente cuando el correo electrónico ya no es solo correo electrónico, sino una ventana a otros servicios? Office 365 tiene un enfoque completo para el [cumplimiento,](../compliance/index.yml)pero el cambio de personas y procesos suele ser mucho más difícil que la tecnología.

Hay muchas otras personas y implicaciones del proceso. En mi opinión, este es un área crítica y poco discutida. Quizás más en otro artículo.

## <a name="tenant-structure-options"></a>Opciones de estructura de inquilinos

### <a name="single-tenant-vs-multi-tenant"></a>Inquilino único frente a multiinquilino

En general, la mayoría de los clientes deben tener solo un inquilino de producción. Hay muchas razones por las que varios inquilinos son desafiantes (darle una búsqueda de [Bing)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)o leer esta [whitepaper](https://aka.ms/multi-tenant-user). Al mismo tiempo, muchos clientes empresariales con los que trabajo tienen otro inquilino (pequeño) para aprendizaje, pruebas y experimentación de TI. El acceso de Azure entre inquilinos es más fácil con [Azure Lighthouse.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 y muchos otros servicios SaaS tienen límites para escenarios entre inquilinos. Hay mucho que tener en cuenta en escenarios [B2B de Azure AD.](/azure/active-directory/b2b/what-is-b2b)

Muchos clientes terminan con varios inquilinos de producción después de una fusión y adquisición (M&A) y desean consolidarse. Hoy en día eso no es sencillo y requeriría Servicios de consultoría de Microsoft (MCS) o un partner más software de terceros. Hay trabajo de ingeniería en curso para abordar diversos escenarios con clientes multiinquilino en el futuro.

Algunos clientes eligen ir con más de un inquilino. Esta debe ser una decisión muy cuidadosa y casi siempre basada en motivos de negocio. Algunos ejemplos son los siguientes:

- Una estructura de empresa de tipo de retención en la que no es necesaria una colaboración fácil entre diferentes entidades y hay necesidades administrativas y de aislamiento muy fuertes.
- Después de una adquisición, se toma una decisión empresarial para mantener dos entidades separadas.
- Simulación del entorno de un cliente que no cambia el entorno de producción del cliente. 
- Desarrollo de software para clientes.

En estos escenarios multiinquilino, los clientes suelen querer mantener la misma configuración en todos los inquilinos o informar sobre los cambios y derivas de configuración. Esto suele significar pasar de los cambios manuales a la configuración como código. El soporte técnico de Microsoft Premiere ofrece un taller para este tipo de requisitos basados en esta IP pública: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .

### <a name="multi-geo"></a>Multi-Geo

Para [Multi-Geo](../enterprise/microsoft-365-multi-geo.md) o no para Multi-Geo, esa es la pregunta. Con Office 365 Multi-Geo, puede aprovisionar y almacenar datos en reposo en las ubicaciones geográficas que haya elegido para cumplir los requisitos [de residencia de](../enterprise/o365-data-locations.md) datos. Hay muchos conceptos erróneos sobre esta funcionalidad. Tenga en cuenta lo siguiente:

- No proporciona ventajas de rendimiento. Podría empeorar el rendimiento si el diseño [de red](https://aka.ms/office365networking) no es correcto. Obtener dispositivos "cercanos" a la red de Microsoft, no necesariamente a los datos.
- No es una solución para el cumplimiento [del RGPD.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) El RGPD no se centra en la soberanía de los datos ni en las ubicaciones de almacenamiento. Existen otros marcos de cumplimiento para ello.
- No resuelve la delegación de administración (vea a continuación) ni las [barreras de información](../compliance/information-barriers.md).
- No es lo mismo que multiinquilino y requiere flujos de trabajo de [aprovisionamiento de](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md) usuarios adicionales.
- No mueve el [espacio empresarial](../enterprise/moving-data-to-new-datacenter-geos.md) (azure AD) a otra geografía. 

## <a name="delegation-of-administration"></a>Delegación de administración

En la mayoría de las organizaciones grandes, la separación de funciones y el control de acceso basado en roles (RBAC) es una realidad necesaria. Voy a pedirme disculpas antes de tiempo. Esto no es tan sencillo como algunos clientes quieren que sea. Los requisitos de cliente, legales, de cumplimiento y otros son diferentes y, a veces, en conflicto en todo el mundo. La simplicidad y la flexibilidad suelen estar en lados opuestos entre sí. No me mal conste, podemos hacer un mejor trabajo en esto. Ha habido (y habrá) mejoras significativas con el tiempo. Visite su Centro de tecnología de [Microsoft](https://www.microsoft.com/mtc) local para averiguar el modelo que se ajusta a sus requisitos empresariales sin leer documentos de 379230. Aquí, me centraré en lo que debería pensar y no en por qué es así. A continuación se muestran cinco áreas diferentes para planear y algunas de las preguntas comunes que he encontrado.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Centros de administración de Azure AD y Microsoft 365

Hay una larga y creciente lista de roles [integrados.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Cada función consta de una lista de permisos de función agrupados para permitir que se realicen acciones específicas. Puede ver estos permisos en la pestaña "Descripción" dentro de cada rol. Como alternativa, puede ver una versión más legible de estos en el Centro de administración de Microsoft 365. Las definiciones de roles integrados no se pueden modificar. Por lo general, los agrupa en tres categorías:

- **Administrador global:** este rol "todo eficaz" debe estar [altamente protegido](../enterprise/protect-your-global-administrator-accounts.md) como lo haría en otros sistemas. Entre las recomendaciones típicas se incluyen: sin asignación permanente y usar Azure AD Privileged Identity Management (PIM); autenticación segura; y así sucesivamente. Es interesante que este rol no le dé acceso a todo de forma predeterminada. Por lo general, veo confusión sobre el acceso de cumplimiento y el acceso de Azure, que se describe más adelante. Sin embargo, este rol siempre puede asignar acceso a otros servicios en el espacio empresarial. 
- **Administradores de servicios específicos:** algunos servicios (Exchange, SharePoint, Power BI, entre otros) consumen roles de administración de alto nivel de Azure AD. Esto no es coherente en todos los servicios y hay más roles específicos del servicio que se debate más adelante.
- **Funcional:** hay una larga (y creciente) lista de roles centrados en operaciones específicas (invitado invitado, y así sucesivamente). Periódicamente, se agregan más de estos en función de las necesidades del cliente.

No es posible delegar todo (aunque la diferencia está disminuyendo), lo que significa que el rol de administrador global tendría que usarse a veces. La configuración como código y la automatización deben considerarse en lugar de la pertenencia de personas a este rol.

**Nota:** El Centro de administración de Microsoft 365 tiene una interfaz más fácil de usar, pero tiene un subconjunto de capacidades en comparación con la experiencia de administración de Azure AD. Ambos portales usan los mismos roles de Azure AD, por lo que los cambios se producen en el mismo lugar. Sugerencia: si desea una interfaz de usuario de administrador centrada en la administración de identidades sin todo el desorden de Azure, use [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

¿Cuál es el nombre? No hagas suposiciones a partir del nombre del rol. El idioma no es una herramienta muy precisa. El objetivo debe ser definir las operaciones que deben delegarse antes de ver qué roles son necesarios. Agregar a alguien al rol "Lector de seguridad" no hace que vean la configuración de seguridad en todo.

La capacidad de crear [roles personalizados](/azure/active-directory/users-groups-roles/roles-custom-overview) es una pregunta común. Esto es limitado en Azure AD hoy (vea a continuación), pero crecerá en capacidades con el tiempo. Las veo como aplicables a las funciones de Azure AD y no pueden abarcar "abajo" el modelo de jerarquía (se ha mencionado anteriormente). Siempre que trato con "personalizado", tiendo a volver a mi director de "simple es mejor".

Otra cuestión común es la capacidad de ámbito de roles en un subconjunto de un directorio. Un ejemplo es algo así como "Administrador del departamento de soporte técnico solo para usuarios de la UE". [Las unidades](/azure/active-directory/users-groups-roles/directory-administrative-units) administrativas (AU) están diseñadas para solucionar este problema. Al igual que antes, creo que son aplicables a las funciones de Azure AD y no pueden abarcar "hacia abajo". Por supuesto, ciertos roles no tienen sentido en el ámbito (administradores globales, administradores de servicio, entre otros).

Hoy en día, todos estos roles requieren pertenencia directa (o asignación dinámica si usa [PIM de Azure AD](/azure/active-directory/privileged-identity-management/)). Esto significa que los clientes deben administrarlas directamente en Azure AD y no pueden basarse en una pertenencia a un grupo de seguridad. No soy un fan de crear scripts para administrarlos, ya que tendría que ejecutarse con derechos elevados. Por lo general, recomiendo la integración de la API con sistemas de procesos como ServiceNow o el uso de herramientas de gobierno de partners como Saviynt. Hay trabajo de ingeniería que se va a solucionar con el tiempo.

Mencioné [PIM de Azure AD](/azure/active-directory/privileged-identity-management/) varias veces. Hay una solución de Administración de [](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) acceso privilegiado (PAM) de Microsoft Identity Manager (MIM) correspondiente para controles locales. También es posible que desee ver [privileged access workstations (PAWs)](/windows-server/identity/securing-privileged-access/privileged-access-workstations) y [Azure AD Identity Governance](/azure/active-directory/governance/identity-governance-overview). También hay varias herramientas de terceros, que pueden habilitar la elevación de roles just-in-time, just-enough y dynamic role elevation. Esto suele formar parte de una discusión más amplia para proteger un entorno. 

A veces, los escenarios llaman para agregar un usuario externo a un rol (vea la sección multiinquilino, arriba). Esto funciona bien. [Azure AD B2B](/azure/active-directory/b2b/) es otro tema grande y divertido para que los clientes puedan recorrerlo, tal vez en otro artículo.

### <a name="security-and-compliance-center-scc"></a>Centro de seguridad y cumplimiento (SCC)

Los permisos del Centro de seguridad y cumplimiento de [Office 365 & son](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) una colección de "grupos de roles", que son independientes y distintos de los roles de Azure AD. Esto puede resultar confuso porque algunos de estos grupos de roles tienen el mismo nombre que los roles de Azure AD (por ejemplo, Lector de seguridad), pero pueden tener una pertenencia diferente. Prefero el uso de roles de Azure AD. Cada grupo de roles consta de uno o más "roles" (vea lo que quiero decir acerca de volver a usar la misma palabra)) y tienen miembros de Azure AD, que son objetos habilitados para correo electrónico. Además, puede crear un grupo de roles con el mismo nombre que un rol, que puede contener o no esa función (evite esta confusión).

En cierto sentido, se trata de una evolución del modelo de grupos de roles de Exchange. Sin embargo, Exchange Online tiene su propia [interfaz de administración de grupos de](/exchange/permissions-exo) roles. Algunos grupos de roles de Exchange Online se bloquean y administran desde Azure AD o el Centro de cumplimiento de & de seguridad, pero otros pueden tener los mismos nombres o similares y se administran en Exchange Online (lo que se agrega a la confusión). Le recomiendo que evite usar la interfaz de usuario de Exchange Online a menos que necesite ámbitos para la administración de Exchange.

No puede crear roles personalizados. Los roles se definen mediante los servicios creados por Microsoft y crecerán a medida que se introduzcan nuevos servicios. Esto es similar en concepto a [los roles definidos por las aplicaciones](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) en Azure AD. Cuando se habilitan nuevos servicios, a menudo es necesario crear nuevos grupos de roles para conceder o delegar el acceso a estos (por ejemplo, la administración de [riesgos de insider](../compliance/insider-risk-management-configure.md?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)).

Estos grupos de roles también requieren pertenencia directa y no pueden contener grupos de Azure AD. Desafortunadamente, estos grupos de roles no son compatibles con PIM de Azure AD. Al igual que los roles de Azure AD, suelo recomendar la administración de estos a través de API o un producto de gobierno de partners como Saviynt u otros.

Las & del Centro de seguridad y cumplimiento abarcan Microsoft 365 y no puede establecer el ámbito de estos grupos de roles en un subconjunto del entorno (como puede hacer con las unidades administrativas de Azure AD). Muchos clientes preguntan cómo pueden subdelegarse. Por ejemplo, "crear una directiva DLP solo para los usuarios de la UE". Hoy en día, si tiene derechos sobre una función específica en el Centro de seguridad & cumplimiento, tiene derechos sobre todo lo que cubre esta función en el espacio empresarial. Sin embargo, muchas directivas tienen capacidades para dirigirse a [](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) un subconjunto del entorno (por ejemplo, "hacer que estas etiquetas estén disponibles solo para estos usuarios"). El gobierno y la comunicación adecuados son un componente clave para evitar conflictos. Algunos clientes eligen implementar un enfoque de "configuración como código" para abordar la subdelegación en el Centro de seguridad & cumplimiento. Algunos servicios específicos admiten subdelegaciones (vea a continuación).

Vale la pena señalar que los controles administrados actualmente a través del Centro de seguridad & y cumplimiento (protection.office.com) están en proceso de migrarse a dos portales de administración independientes: security.microsoft.com y compliance.microsoft.com. El cambio es la única constante.

### <a name="service-specific"></a>Específico del servicio

Como se mencionó anteriormente, muchos clientes buscan lograr un modelo de delegación más detallado. Un ejemplo común: "Administrar el servicio XYZ solo para usuarios y ubicaciones de división X" (o alguna otra dimensión). La capacidad para hacerlo depende de cada servicio y no es coherente en todos los servicios y capacidades. Además, cada servicio puede tener un modelo RBAC independiente y único. En lugar de hablar de todos estos (llevará para siempre), estoy agregando vínculos relevantes para cada servicio. Esta no es una lista completa, pero le ayudará a empezar.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](/microsoftteams/itadmin-readiness)
- **Exhibición de documentos electrónicos** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](../compliance/index.yml) 
  + **Filtrado de permisos**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](../compliance/index.yml)
  + **Límites de cumplimiento**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](../compliance/set-up-compliance-boundaries.md)
  + **Exhibición de documentos electrónicos avanzada**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](../compliance/overview-ediscovery-20.md)
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](../enterprise/add-a-sharepoint-geo-admin.md) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](/dynamics365/) <br>
  Nota: este vínculo se encuentra en la raíz de la documentación. Hay varios tipos de servicios con variaciones en el modelo de administración y delegación.
- **Power Platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](/power-platform/admin/admin-documentation)
  + **Power Apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](/power-platform/admin/wp-security) <br>
    Nota: hay varios tipos con variaciones en los modelos de administración y delegación.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](/power-automate/environments-overview-admin)
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](/power-bi/service-admin-governance) <br>
Nota: la seguridad y delegación de la plataforma de datos (que Power BI es un componente) es un área compleja.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](/mem/intune/fundamentals/role-based-access-control)
- **Microsoft Defender para endpoint**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](../security/defender/m365d-permissions.md)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](/stream/assign-administrator-user-role)
- **Barreras de información**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](../compliance/information-barriers.md)

Para el resto, la búsqueda en Docs ha sido realmente buena en los últimos tiempos - [https://docs.microsoft.com/](../compliance/information-barriers.md) . 

### <a name="activity-logs"></a>Registros de actividad

Office 365 tiene un [registro de auditoría unificado.](../compliance/search-the-audit-log-in-security-and-compliance.md) Es un registro [muy detallado,](/office/office-365-management-api/office-365-management-activity-api-schema)pero no lea demasiado en el nombre. Puede que no contenga todo lo que desee o necesite para sus necesidades de seguridad y cumplimiento. Además, algunos clientes están realmente interesados en [la auditoría avanzada](../compliance/advanced-audit.md).

Algunos ejemplos de registros de Microsoft 365 a los que se tiene acceso a través de otras API son los siguientes:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (actividades no relacionadas con Office 365)
- [Seguimiento de mensajes de Exchange](/powershell/module/exchange/get-messagetrace)
- Sistemas threat/UEBA mencionados anteriormente (por ejemplo, Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender para endpoint, entre otros)
- [Protección de información de Microsoft](../compliance/data-classification-activity-explorer.md?view=o365-worldwide)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Es importante identificar primero todos los orígenes de registro necesarios para un programa de seguridad y cumplimiento. Tenga en cuenta también que los distintos registros tienen diferentes límites de retención en línea. 

Desde la perspectiva de delegación de administración, la mayoría de los registros de actividad de Microsoft 365 no tienen un modelo RBAC integrado. Si tiene permiso para ver un registro, puede ver todo en él. Un ejemplo común de un requisito de cliente es: "Quiero poder consultar la actividad solo para los usuarios de la UE" (o cualquier otra dimensión). Para lograr este requisito, debemos transferir registros a otro servicio. En la nube de Microsoft, se recomienda transferirla a [Azure Sentinel](/azure/sentinel/overview) o [Log Analytics.](/azure/azure-monitor/learn/quick-create-workspace) 

Diagrama de alto nivel:

![diagrama de orígenes de registro para un programa de seguridad y cumplimiento](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

El diagrama anterior representa las capacidades integradas para enviar registros a Event Hub y/o Azure Storage o Azure Log Analytics. Todavía no todos los sistemas incluyen esta opción. Pero hay otros métodos para enviar estos registros al mismo repositorio. Por ejemplo, vea [Protecting your Teams with Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

La combinación de todos los registros en una ubicación de almacenamiento incluye ventajas adicionales, como correlaciones cruzadas, tiempos de retención personalizados, aumento con datos necesarios para admitir el modelo RBAC, y así sucesivamente. Una vez que los datos están en este sistema de almacenamiento, puede crear un panel de Power BI (u otro tipo de visualización) con un modelo RBAC adecuado.

Los registros no tienen que dirigirse a un solo lugar. También puede ser beneficioso integrar registros de [Office 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) con Microsoft Cloud App Security o un modelo RBAC personalizado en [Power BI.](../admin/usage-analytics/usage-analytics.md?view=o365-worldwide) Los diferentes repositorios tienen diferentes ventajas y audiencias.

Vale la pena mencionar que hay un sistema de análisis integrado muy enriquecido para seguridad, amenazas, vulnerabilidades, entre otros en un servicio llamado [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md?view=o365-worldwide).

Muchos clientes grandes desean transferir estos datos de registro a un sistema de terceros (por ejemplo, SIEM). Hay diferentes enfoques para esto, pero en general [Azure Event Hub](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) y [Graph](/graph/security-integration) son buenos puntos de partida.

### <a name="azure"></a>Azure

A menudo se me pregunta si hay una forma de separar roles de privilegios altos entre Azure AD, Azure y SaaS (por ejemplo: Administrador global de Office 365, pero no Azure).  La verdad es que no.  La arquitectura multiinquilino es necesaria si se requiere una separación administrativa completa, pero eso agrega una complejidad [significativa](https://aka.ms/multi-tenant-user) (vea más arriba). Todos estos servicios forman parte del mismo límite de seguridad e identidad (consulte el modelo de jerarquía anterior).  

Es importante comprender las relaciones entre varios servicios del mismo inquilino. Estoy trabajando con muchos clientes que están creando soluciones empresariales que abarcan Azure, Office 365 y Power Platform (y a menudo también servicios en la nube locales y de terceros). Un ejemplo común:

1. Deseo colaborar en un conjunto de documentos/imágenes/etc. (Office 365)
2. Enviar cada uno de ellos a través de un proceso de aprobación (Power Platform)
3.  Una vez aprobados todos los componentes, ensamble estos en una API unificada de [Microsoft Graph](/azure/active-directory/develop/microsoft-graph-intro) para entregas (Azure) es su mejor amigo para estos.  No es imposible, pero es mucho más complejo diseñar una solución que abarca [varios inquilinos.](/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) permite una administración de acceso detallada para Azure. Con RBAC, puede administrar el acceso a los recursos concediendo a los usuarios el menor número de permisos necesarios para realizar sus trabajos. Los detalles están fuera del ámbito de este documento, pero para obtener más información sobre RBAC, vea ¿Qué es el control de acceso basado en roles [(RBAC) en Azure?](/azure/role-based-access-control/overview) RBAC es importante, pero solo una parte de las consideraciones de gobierno para Azure. [Cloud Adoption Framework](/azure/cloud-adoption-framework/govern/) es un excelente punto de partida para obtener más información. Me gusta cómo mi amigo, Andrés Ravinet guía a los clientes paso a paso a través de varios componentes para decidir sobre el enfoque. La vista de alto nivel para varios elementos (no es tan buena como el proceso para llegar al modelo de cliente real) es algo así:

![Vista de alto nivel de componentes de Azure para administración delegada](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Como puede ver en la imagen anterior, muchos otros servicios deben considerarse como parte del diseño (por ejemplo: Directivas de [Azure,](/azure/governance/policy/overview)Planos de [Azure,](/azure/governance/blueprints/overview)Grupos de [administración,](/azure/governance/management-groups/)y así sucesivamente).

## <a name="conclusion"></a>Conclusión

Se inició como un resumen breve y terminó por más tiempo de lo que esperaba.  Espero que ahora esté listo para aventurarse en una vista profunda de cómo crear un modelo de delegación para su organización.  Esta conversación es muy común con los clientes. No hay ningún modelo que funcione para todos. Esperar algunas mejoras planeadas de ingeniería de Microsoft antes de documentar patrones comunes que vemos en todos los clientes. Mientras tanto, puede trabajar con su equipo de cuenta de Microsoft para organizar una visita al Centro de tecnología [de Microsoft más cercano.](https://www.microsoft.com/mtc)  Nos vemos allí.