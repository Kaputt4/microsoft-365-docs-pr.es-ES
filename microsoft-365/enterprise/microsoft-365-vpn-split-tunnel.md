---
title: 'Información general: Túnel dividido de VPN para Microsoft 365'
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Información general sobre la tunelización dividida de VPN Microsoft 365 para optimizar la conectividad de los usuarios remotos.
ms.openlocfilehash: 67ce8a38b536dab12af679ba860aac6d974db60e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329077"
---
# <a name="overview-vpn-split-tunneling-for-microsoft-365"></a>Información general: Túnel dividido de VPN para Microsoft 365

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización Microsoft 365 usuarios remotos.

>- Para obtener instrucciones detalladas sobre cómo implementar el túnel dividido de VPN, consulte [Implementing VPN split tunneling for Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener una lista detallada de escenarios de túnel dividido de VPN, consulte [Escenarios de túnel dividido de VPN comunes para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener instrucciones sobre cómo proteger el Teams de medios en entornos de túnel dividido de VPN, consulte [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md).
>- Para obtener información sobre cómo configurar stream y eventos en directo en entornos VPN, consulte [Special considerations for Stream and live events in VPN environments](microsoft-365-vpn-stream-and-live-events.md).
>- Para obtener información sobre cómo optimizar Microsoft 365 el rendimiento de los inquilinos en todo el mundo para los usuarios de China, [vea optimización Microsoft 365 rendimiento para los usuarios de China](microsoft-365-networking-china.md).

Las empresas han usado tradicionalmente VPN para admitir experiencias remotas seguras para sus usuarios. Mientras las cargas de trabajo principales seguían siendo locales, una VPN desde el cliente remoto enrutada a través de un centro de datos en la red corporativa era el método principal para que los usuarios remotos puedan acceder a los recursos corporativos. Para salvaguardar estas conexiones, las empresas crean capas de soluciones de seguridad de red a lo largo de las rutas VPN. Esta seguridad se creó para proteger la infraestructura interna y proteger la navegación móvil de sitios web externos mediante el reenrutación del tráfico en la VPN y, a continuación, a través del perímetro de Internet local. Las VPN, los perímetros de red y la infraestructura de seguridad asociada a menudo se basaban y escalaban para un volumen de tráfico definido, normalmente con la mayor parte de la conectividad iniciada desde la red corporativa y la mayor parte de ella se encontraba dentro de los límites de la red interna.

Durante bastante tiempo, los modelos de VPN en los que todas las conexiones del dispositivo del usuario remoto se enrutan de nuevo a la red local (conocido como _forzar el uso del túnel_) eran en gran medida sostenibles siempre que la escala concurrente de usuarios remotos fuera modesta y los volúmenes de tráfico que atravesaban la VPN fueran bajos.  Algunos clientes siguieron utilizando el túnel de fuerza VPN como el status quo incluso después de que sus aplicaciones se movieron desde el perímetro corporativo a las nubes saas públicas.

El uso de VPN tuneladas forzadas para conectarse a aplicaciones en la nube distribuidas y sensibles al rendimiento es subóptimo, pero algunas empresas han aceptado los efectos negativos para mantener el statu quo de seguridad. A continuación se muestra un diagrama de ejemplo de este escenario:

![Configuración Tunnel VPN forzada.](../media/vpn-split-tunneling/enterprise-network-traditional.png)

_Figura 1: Una solución de VPN Tunnel forzada tradicional._

Este problema ha estado creciendo durante muchos años, ya que muchos clientes informan de un cambio significativo de los patrones de tráfico de red. El tráfico que solía permanecer local ahora se conecta a puntos de conexión de nube externos. Muchos clientes de Microsoft informan que anteriormente, alrededor del 80 % de su tráfico de red era a algún origen interno (representado por la línea punteada en el diagrama anterior). En 2020, ese número disminuyó a alrededor del 20 % o inferior a medida que han desplazado las cargas de trabajo principales a la nube. Estas tendencias no son poco comunes con otras empresas. Con el tiempo, a medida que avanza el recorrido en la nube, el modelo anterior se vuelve cada vez más engorroso e insostenible, lo que impide que una organización sea ágil a medida que avanza a un mundo de primera nube.

La crisis mundial de COVID-19 ha escalado este problema para requerir una corrección inmediata. La necesidad de garantizar la seguridad de los empleados ha generado demandas sin precedentes en TI empresarial para dar soporte a la productividad del trabajo desde el hogar a una escala masiva. Microsoft 365 está bien posicionado para ayudar a los clientes a satisfacer esa demanda, pero la alta concurrencia de los usuarios que trabajan desde casa genera un gran volumen de tráfico de Microsoft 365 que, si se enruta a través de VPN de túnel forzado y perímetros de red locales, provoca una saturación rápida y ejecuta la infraestructura VPN fuera de capacidad. En esta nueva realidad, el uso de VPN para obtener acceso a Microsoft 365 ya no es solo un impedimento de rendimiento, sino un muro duro que no solo afecta Microsoft 365 las operaciones empresariales críticas que aún tienen que depender de la VPN para funcionar.

Microsoft ha estado trabajando estrechamente con los clientes y el sector en general para proporcionar soluciones eficaces y modernas a estos problemas desde nuestros propios servicios y para alinearse con los procedimientos recomendados del sector. [Los principios de](./microsoft-365-network-connectivity-principles.md) conectividad del servicio Microsoft 365 han sido diseñados para funcionar de forma eficaz para los usuarios remotos, al tiempo que permiten a una organización mantener la seguridad y el control sobre su conectividad. Estas soluciones también se pueden implementar rápidamente con un trabajo limitado pero logran un efecto positivo significativo en los problemas descritos anteriormente.

Para los clientes que conectan sus dispositivos de trabajo remoto a la red corporativa o a la infraestructura en la nube a través de VPN, Microsoft recomienda que los escenarios clave Microsoft 365 **Microsoft Teams**, **SharePoint Online** y **Exchange Online** se enruten a través de una configuración de túnel _dividido de VPN_. Esto adquiere especial importancia como estrategia de primera línea para facilitar la productividad continua de los empleados durante eventos de trabajo desde casa a gran escala, como la crisis de COVID-19.

![Dividir Tunnel VPN.](../media/vpn-split-tunneling/vpn-model-2.png)

_Figura 2: Una solución de túnel dividido de VPN con excepciones Microsoft 365 definidas enviadas directamente al servicio. El resto del tráfico atraviesa el túnel VPN independientemente del destino._

La esencia de este enfoque consiste en proporcionar un método sencillo para que las empresas mitiguen el riesgo de saturación de la infraestructura VPN y mejoren considerablemente Microsoft 365 rendimiento en el período de tiempo más corto posible. La configuración de clientes VPN para permitir que el tráfico más importante y de alto volumen Microsoft 365 omitir el túnel VPN obtiene las siguientes ventajas:

- Mitiga inmediatamente la causa raíz de la mayoría de los problemas de rendimiento y capacidad de red notificados por el cliente en arquitecturas vpn empresariales que afectan Microsoft 365 experiencia del usuario
  
  La solución recomendada se dirige específicamente Microsoft 365 de servicio clasificados como **Optimizar** en el tema Microsoft 365 [direcciones URL e intervalos de direcciones IP](./urls-and-ip-address-ranges.md). El tráfico a estos puntos de conexión es muy sensible a la limitación de latencia y ancho de banda, y permitirle omitir el túnel VPN puede mejorar considerablemente la experiencia del usuario final, así como reducir la carga de red corporativa. Microsoft 365 las conexiones que no constituyen la mayoría del ancho de banda o la superficie de la experiencia del usuario pueden seguir enrutadas a través del túnel VPN junto con el resto del tráfico enlazado a Internet. Para obtener más información, consulte [La estrategia de túnel dividido de VPN](#the-vpn-split-tunnel-strategy).

- Los clientes pueden configurar, probar e implementar rápidamente y sin requisitos de infraestructura o aplicación adicionales

  Según la plataforma de VPN y la arquitectura de red, la implementación puede llevar solo unas horas. Para más información, consulte [Implementar túnel dividido de VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Preserva la posición de seguridad de las implementaciones de VPN del cliente sin tener que cambiar la forma en que se enrutan otras conexiones, incluido el tráfico de Internet

  La configuración recomendada sigue el principio del **privilegio mínimo** para las excepciones de tráfico de VPN y permite que los clientes implementen el túnel dividido de VPN sin exponer a los usuarios o a la infraestructura a riesgos de seguridad adicionales. El tráfico de red enrutado directamente Microsoft 365 los puntos de conexión de Microsoft 365 se cifra, se valida para la integridad mediante pilas de aplicaciones cliente y se aplica Office direcciones IP dedicadas Microsoft 365 los servicios de Microsoft 365 que se endurecen tanto en el nivel de aplicación como de red. Para más información, vea [Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto de hoy día (blog del Equipo de seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Es compatible de forma nativa con la mayoría de las plataformas VPN empresariales

  Microsoft continúa colaborando con socios del sector que produzcan soluciones VPN comerciales para ayudar a los asociados a desarrollar guías específicas y plantillas de configuración para sus soluciones según las recomendaciones anteriores. Para obtener más información, vea [Tutoriales para las plataformas VPN comunes](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft recomienda centrar la configuración de VPN de túnel dividido en intervalos IP dedicados documentados para Microsoft 365 servicios. Es posible que las configuraciones de túnel dividido basadas en FQDN o AppID, aunque sea posible en determinadas plataformas cliente VPN, no cubran completamente los escenarios clave Microsoft 365 y puedan estar en conflicto con las reglas de enrutamiento de VPN basadas en IP. Por este motivo, Microsoft no recomienda usar Microsoft 365 FQDN para configurar vpn de túnel dividido. El uso de la configuración FQDN puede resultar útil en otros escenarios similares, como la personalización de archivos .pac o la implementación de omisión de proxy.

Para obtener instrucciones de implementación completa, consulte [Implementing VPN split tunneling for Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).

Para obtener un proceso paso a paso para configurar Microsoft 365 para los trabajadores remotos, consulte [Configurar la infraestructura para el trabajo remoto](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>La estrategia de túneles divididos de VPN

Las redes corporativas tradicionales suelen diseñarse para trabajar de forma segura en estructuras prenube en las que la mayoría de los datos, servicios y aplicaciones importantes se hospedan de forma local y se conectan directamente a la red corporativa interna, al igual que la mayoría de los usuarios. Por lo tanto, la infraestructura de red se crea en torno a estos elementos. Las oficinas delegadas se conectan a la oficina central _a través de redes de Alternancia de etiquetas multiprotocolo (MPLS)_ y los usuarios remotos deben conectarse a la red corporativa a través de una VPN para acceder a los puntos de conexión locales y a Internet. En este modelo, todo el tráfico de usuarios remotos recorre la red corporativa y se enruta al servicio en la nube mediante un punto de salida común.

![Configuración de VPN forzada.](../media/vpn-split-tunneling/vpn-model-1.png)

_Figura 2: una solución de VPN común para usuarios remotos en la que todo el tráfico se transfiere de nuevo obligatoriamente a la red corporativa, independientemente del destino_

A medida que las organizaciones mueven datos y aplicaciones a la nube, este modelo ha comenzado a ser menos eficaz a medida que rápidamente se vuelve engorroso, caro e incalable, lo que afecta significativamente al rendimiento y la eficiencia de la red de los usuarios y restringe la capacidad de la organización para adaptarse a las necesidades cambiantes. Numerosos clientes de Microsoft han informado de que hace unos años el 80 % del tráfico de red estaba en un destino interno, pero en 2020 el 80 % más del tráfico se conecta a un recurso externo basado en la nube.

La crisis del COVID-19 ha agravado el problema de requerir soluciones inmediatas para la inmensa mayoría de las organizaciones. Muchos clientes han descubierto que el modelo de VPN forzoso no es lo suficientemente escalable ni tampoco es adecuado para el 100 % de escenarios de trabajo remoto como el que necesita esta crisis. Se necesitan soluciones rápidas para que estas organizaciones sigan funcionando de forma eficiente.

Para el servicio de Microsoft 365, Microsoft ha diseñado los requisitos de conectividad para el servicio teniendo en cuenta este problema de forma cuadrada, donde un conjunto de extremos de servicio centrado, estrechamente controlado y relativamente estático se puede optimizar de forma muy sencilla y rápida para ofrecer un alto rendimiento para los usuarios que acceden al servicio y reducir la carga en la infraestructura VPN para que pueda ser usada por el tráfico que aún lo requiere.

Microsoft 365 categoriza los puntos de conexión necesarios para Microsoft 365 en tres categorías: **Optimize**, **Allow** y **Default**. **Optimizar** los puntos de conexión es nuestra meta aquí y presenta las siguientes características:

- Son los puntos de conexión que pertenecen a Microsoft, que también se encarga de administrarlos y alojarlos en su infraestructura.
- Están dedicados a cargas de Microsoft 365 principales como Exchange Online, SharePoint Online, Skype Empresarial Online y Microsoft Teams
- Se les ofrece IP
- Tienen una baja tasa de cambio y un número esperado reducido (actualmente, 20 subredes IP)
- Tienen un alto volumen o son sensibles a la latencia.
- Se les puede proporcionar elementos de seguridad necesarios directamente en el servicio en lugar de en línea en la red.
- Cuenta con alrededor del 70-80 % del volumen de tráfico al servicio Microsoft 365 cliente

Este conjunto de puntos de conexión con ámbito estrecho se puede dividir fuera del túnel VPN forzado y enviarse de forma segura y directa al servicio Microsoft 365 a través de la interfaz local del usuario. Esto es conocido como **túnel dividido**.

Los elementos de seguridad como DLP, protección antivirus, autenticación y control de acceso se pueden entregar de forma mucho más eficaz en estos puntos de conexión en diferentes capas del servicio. As we also divert the bulk of the traffic volume away from the VPN solution, this frees the VPN capacity up for business critical traffic that still relies on it. Asimismo, en muchos casos elimina la necesidad de usar un programa de actualización prolongado y costoso que pueda lidiar con esta nueva forma de operar.

![Dividir Tunnel de configuración de VPN.](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Figura 3: Una solución de túnel dividido de VPN con excepciones Microsoft 365 definidas enviadas directamente al servicio. El resto del tráfico se vuelve a forzar a la red corporativa independientemente del destino._

Desde el punto de vista de la seguridad, Microsoft tiene una serie de características que pueden ofrecer una seguridad similar, o incluso mejor que la ofrecida por la inspección en línea de las pilas de seguridad locales. La entrada de blog del equipo de seguridad de Microsoft [Alternativas para que los profesionales de la seguridad y de TI puedan lograr controles de seguridad modernos en los escenarios de trabajo remoto actuales](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) resume claramente las características disponibles y encontrará instrucciones más detalladas en este artículo. También puede leer acerca de la implementación de Microsoft del túnel dividido de VPN en[Ejecutando en VPN: cómo Microsoft mantiene conectada a su fuerza de trabajo remota.](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

En la mayoría de los casos, esta implementación puede alcanzarse en cuestión de horas, solucionando rápidamente uno de los problemas más apremiantes de las organizaciones a la hora de extender los servicios de trabajo remoto a toda la empresa. Para obtener instrucciones de implementación de túnel dividido de VPN, consulte [Implementing VPN split tunneling for Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="faq"></a>Preguntas más frecuentes

El equipo de seguridad de Microsoft ha publicado Formas alternativas para que los profesionales de seguridad y TI puedan lograr controles de seguridad [modernos en los escenarios](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) de trabajo remoto únicos de hoy en día, una entrada de blog que describe formas clave para que los profesionales de seguridad y TI puedan lograr controles de seguridad modernos en los escenarios de trabajo remoto únicos actuales. Además, a continuación se muestran algunas de las preguntas de los clientes más comunes acerca de este tema, con sus respuestas.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>¿Cómo puedo evitar que los usuarios tengan acceso a otros inquilinos en los que se pueden filtrar datos?

La respuesta es una [característica denominada restricciones de inquilino](/azure/active-directory/manage-apps/tenant-restrictions). El tráfico de autenticación no es de gran volumen ni especialmente confidencial de latencia, por lo que se puede enviar a través de la solución VPN al proxy local donde se aplica la característica. Aquí se mantiene una lista de inquilinos de confianza y si el cliente intenta obtener un token para un inquilino que no es de confianza, el proxy simplemente deniega la solicitud. Si el inquilino es de confianza, se puede obtener el token si el usuario tiene las credenciales y los derechos adecuados.

Por lo tanto, aunque un usuario pueda realizar una conexión TCP/UDP a los puntos de conexión marcados anteriormente para Optimizar, sin un token válido para tener acceso al espacio empresarial en cuestión, simplemente no puede iniciar sesión ni acceder a los datos ni moverlo.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>¿Permite este modelo el acceso a los servicios al consumidor, como cuentas de OneDrive personales?

No, no es así, los puntos de conexión Microsoft 365 no son los mismos que los servicios de consumidor (Onedrive.live.com como ejemplo) por lo que el túnel dividido no permitirá que un usuario acceda directamente a los servicios de consumidor. El tráfico a los puntos de conexión de consumidor seguirá utilizando el túnel VPN y seguirán aplicándose las directivas existentes.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>¿Cómo puedo aplicar DLP y proteger mis datos confidenciales cuando el tráfico ya no circule por la solución local?

Para ayudarle a evitar la divulgación accidental de información confidencial, Microsoft 365 un amplio conjunto de herramientas [integradas](../compliance/information-protection.md). Puede usar las [funciones integradas de DLP](../compliance/dlp-learn-about-dlp.md) de Teams y SharePoint para detectar información confidencial compartida o almacenada de forma no adecuada. Si parte de la estrategia de trabajo remoto implica una directiva bring-your-own-device (BYOD), puedes usar el [](/azure/active-directory/conditional-access/app-based-conditional-access) acceso condicional basado en aplicaciones para evitar que los datos confidenciales se descarguen en los dispositivos personales de los usuarios

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>¿Cómo puedo evaluar y mantener el control de la autenticación de los usuarios cuando se conectan directamente?

Además de la característica de restricciones de inquilino que se indicó en la P1, se pueden aplicar [directivas de acceso condicional](/azure/active-directory/conditional-access/overview) para evaluar dinámicamente el riesgo de una solicitud de autenticación y reaccionar de forma adecuada. Microsoft recomienda que el modelo [de](https://www.microsoft.com/security/zero-trust?rtc=1) confianza cero se implemente con el tiempo y podemos usar Azure AD de acceso condicional para mantener el control en un mundo móvil y en la nube. Las directivas de acceso condicional se pueden usar para tomar decisiones en tiempo real acerca de si una solicitud de autenticación es satisfactoria basándose en varios factores, como:

- Dispositivo, ¿se ha unido un dominio conocido o de confianza?
- IP, ¿la solicitud de autenticación proviene de una dirección IP corporativa conocida? ¿O de un país en el que no confíe?
- Aplicación, ¿está autorizado el usuario a usar esta aplicación?

Entonces se puede desencadenar una directiva como aprobar, activar MFA o bloquear la autenticación de acuerdo con estas directivas.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>¿Cómo puedo protegerme contra virus y malware?

De nuevo, Microsoft 365 proporciona protección para los extremos marcados de Optimize en varias capas del propio servicio, que se describen [en este documento](/office365/Enterprise/office-365-malware-and-ransomware-protection). Como se ha indicado, es mucho más eficaz proporcionar estos elementos de seguridad en el propio servicio en lugar de intentar hacerlo en línea con dispositivos que pueden no comprender completamente los protocolos o el tráfico. De forma predeterminada, SharePoint Online [examina automáticamente las cargas de archivos](../security/office-365-security/virus-detection-in-spo.md) en busca de malware conocido

Para los puntos de conexión Exchange mencionados anteriormente, [Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) y [Microsoft Defender para Microsoft 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) realizar un excelente trabajo de proporcionar seguridad del tráfico al servicio.

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>¿Puedo enviar algo más de forma directa que el tráfico de Optimizar?

Se debe dar prioridad a los puntos de conexión marcados como **Optimizar**, ya que aportan el máximo beneficio con un bajo nivel de trabajo. Sin embargo, si lo desea, es necesario permitir puntos de conexión marcados para que el servicio funcione y que se proporcionan direcciones IP para los puntos de conexión que se pueden usar si es necesario.

También hay varios proveedores que ofrecen soluciones de seguridad y proxy basadas en la nube denominadas puertas de enlace _web seguras_ que proporcionan seguridad central, control y aplicación de directiva corporativa para la exploración web general. Estas soluciones pueden funcionar bien en un mundo de primera nube, si es altamente disponible, eficaz y aprovisionado cerca de los usuarios al permitir que el acceso seguro a Internet se entregue desde una ubicación basada en la nube cercana al usuario. Esto elimina la necesidad de una horquilla a través de la red VPN/corporativa para el tráfico de exploración general, a la vez que se permite el control de seguridad central.

Sin embargo, incluso con estas soluciones en su lugar, Microsoft sigue recomendando encarecidamente que optimice el tráfico Microsoft 365 marcado se envía directamente al servicio.

Para obtener instrucciones sobre cómo permitir el acceso directo a una red virtual de Azure, consulte [Remote work using Azure VPN Gateway Point-to-site](/azure/vpn-gateway/work-remotely-support).

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>¿Por qué es necesario el puerto 80? ¿El tráfico se envía sin cifrar?

El puerto 80 solo se usa para cosas como redirigirse a una sesión de puerto 443, no se envían datos de clientes ni se obtiene acceso a ellos a través del puerto 80. [El](../compliance/encryption.md) cifrado describe el cifrado de datos en tránsito y en reposo para Microsoft 365, y [Tipos](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) de tráfico describe cómo usamos SRTP para proteger el tráfico Teams multimedia.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>¿Se aplica este consejo a los usuarios de China que usan una instancia mundial de Microsoft 365?

**No**. La única advertencia a los consejos anteriores son los usuarios del PRC que se conectan a una instancia mundial de Microsoft 365. Como la congestión en la red de servicios transfronterizos es habitual en la región, el rendimiento de salida de Internet directo puede variar. La mayoría de los clientes de la región operan con una VPN para dirigir el tráfico a la red corporativa y usan su circuito de MPLS autorizado o similares para realizar la salida fuera del país mediante una ruta optimizada. Esto se describe más adelante en el artículo Microsoft 365 [optimización del rendimiento para los usuarios de China](microsoft-365-networking-china.md).

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>¿Funciona la configuración de túnel dividido Teams se ejecuta en un explorador?

Sí, con advertencias. La Teams funcionalidad se admite en los exploradores que se enumeran en [Obtener clientes para Microsoft Teams](/microsoftteams/get-clients#web-client).

Además, Microsoft Edge **96** y posteriores admiten el túnel dividido de VPN para el tráfico punto a punto habilitando la directiva [Edge WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled). En este momento, es posible que otros exploradores no admitan el túnel dividido de VPN para el tráfico punto a punto.

## <a name="related-articles"></a>Artículos relacionados

[Implementación de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[Escenarios comunes de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Proteger el tráfico Teams multimedia para el túnel dividido de VPN](microsoft-365-vpn-securing-teams.md)

[Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365 optimización del rendimiento para usuarios de China](microsoft-365-networking-china.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Microsoft 365 de red y rendimiento](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
