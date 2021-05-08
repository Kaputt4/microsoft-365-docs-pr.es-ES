---
title: 'Resumen: túnel dividido VPN con Office 365'
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Guía para usar el túnel dividido VPN con Office 365 para optimizar la conectividad de Office 365 para usuarios remotos.
ms.openlocfilehash: c92599469431732136637cee2bb6a029c4eb4037
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259252"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Optimizar la conectividad de Office 365 para usuarios remotos usando el túnel dividido de VPN
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

Para los clientes que conectan sus dispositivos de trabajo remoto a la red corporativa o a la infraestructura en la nube a través de VPN, Microsoft recomienda que los escenarios clave Office 365 **Microsoft Teams,** **SharePoint Online** y **Exchange Online** se enruten a través de una configuración de túnel dividido de _VPN._ Esto adquiere especial importancia como estrategia de primera línea para facilitar la productividad continua de los empleados durante eventos de trabajo desde casa a gran escala, como la crisis de COVID-19.

![Configuración del túnel dividido de VPN](../media/vpn-split-tunneling/vpn-model-2.png)

_Figura 1: una solución de túnel dividido de VPN con excepciones de Office 365 definidas enviada directamente al servicio. El resto del tráfico recorre el túnel de VPN independientemente del destino._

La meta de este enfoque es ofrecer un método sencillo para que las empresas puedan mitigar el riesgo de la saturación de la infraestructura de VPN y mejorar considerablemente el rendimiento de Office 365 en el período de tiempo más reducido posible. Configurar los clientes de VPN para que permitan el tráfico de Office 365 más importante y de mayor volumen permite eludir el túnel VPN y, además, aporta las siguientes ventajas:

- Atenúa de inmediato la causa principal de la mayoría de los problemas de rendimiento y de capacidad de red detectados en clientes con arquitecturas VPN empresariales que afectan a la experiencia de usuario de Office 365.
  
  La solución recomendada se dirige específicamente a los puntos de conexión de servicio de Office 365 categorizados como **Optimizar** en el tema [URL e intervalos de direcciones IP de Office 365](./urls-and-ip-address-ranges.md). El tráfico a estos puntos de conexión es muy sensible a la limitación de latencia y ancho de banda, y permitirle omitir el túnel VPN puede mejorar considerablemente la experiencia del usuario final, así como reducir la carga de red corporativa. Las conexiones de Office 365 que no supongan la mayor parte del ancho de banda o no dejen una gran huella en la experiencia de usuario se pueden enrutar a través del túnel VPN junto con el resto del tráfico vinculado a Internet. Para obtener más información, consulte [La estrategia de túnel dividido de VPN](#the-vpn-split-tunnel-strategy).

- Los clientes pueden configurar, probar e implementar rápidamente y sin requisitos de infraestructura o aplicación adicionales

  Según la plataforma de VPN y la arquitectura de red, la implementación puede llevar solo unas horas. Para más información, consulte [Implementar túnel dividido de VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Preserva la posición de seguridad de las implementaciones de VPN del cliente sin tener que cambiar la forma en que se enrutan otras conexiones, incluido el tráfico de Internet

  La configuración recomendada sigue el principio del **privilegio mínimo** para las excepciones de tráfico de VPN y permite que los clientes implementen el túnel dividido de VPN sin exponer a los usuarios o a la infraestructura a riesgos de seguridad adicionales. El tráfico de red que se enruta directamente Office 365 los puntos de conexión de Office 365 se cifra, se valida para la integridad mediante pilas de aplicaciones cliente y se aplica Office direcciones IP dedicadas Office 365 los servicios de Office 365 que se endurecen tanto en el nivel de aplicación como en el nivel de red. Para más información, vea [Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto de hoy día (blog del Equipo de seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Es compatible de forma nativa con la mayoría de las plataformas VPN empresariales

  Microsoft continúa colaborando con socios del sector que produzcan soluciones VPN comerciales para ayudar a los asociados a desarrollar guías específicas y plantillas de configuración para sus soluciones según las recomendaciones anteriores. Para obtener más información, vea [Tutoriales para las plataformas VPN comunes](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft recomienda aplicar la configuración de túnel dividido de VPN a intervalos de IP dedicados ya documentados para los servicios de Office 365. Aunque es posible en determinadas plataformas cliente de VPN utilizar configuraciones de túnel dividido basadas en FQDN o AppID, estas pueden no cubrir completamente los escenarios clave de Office 365 y pueden entrar en conflicto con las reglas de enrutamiento VPN basadas en IP. Por este motivo, Microsoft no recomienda usar FQDN de Office 365 para configurar el túnel dividido de VPN. El uso de la configuración FQDN puede resultar útil en otros escenarios similares, como la personalización de archivos .pac o la implementación de omisión de proxy.

Para obtener una orientación completa sobre la implementación, consulte [Implementación del túnel dividido de VPN para Office 365](microsoft-365-vpn-implement-split-tunnel.md).

Para obtener un proceso paso a paso para configurar Microsoft 365 para los trabajadores [remotos,](..\solutions\empower-people-to-work-remotely.md) vea Configurar la infraestructura para el trabajo remoto

## <a name="the-vpn-split-tunnel-strategy"></a>La estrategia de túneles divididos de VPN

Las redes corporativas tradicionales suelen diseñarse para trabajar de forma segura en estructuras prenube en las que la mayoría de los datos, servicios y aplicaciones importantes se hospedan de forma local y se conectan directamente a la red corporativa interna, al igual que la mayoría de los usuarios. Por lo tanto, la infraestructura de red se crea en torno a estos elementos. Las oficinas delegadas se conectan a la oficina central _a través de redes de Alternancia de etiquetas multiprotocolo (MPLS)_ y los usuarios remotos deben conectarse a la red corporativa a través de una VPN para acceder a los puntos de conexión locales y a Internet. En este modelo, todo el tráfico de usuarios remotos recorre la red corporativa y se enruta al servicio en la nube mediante un punto de salida común.

![Configuración de VPN forzada](../media/vpn-split-tunneling/vpn-model-1.png)

_Figura 2: una solución de VPN común para usuarios remotos en la que todo el tráfico se transfiere de nuevo obligatoriamente a la red corporativa, independientemente del destino_

A medida que las organizaciones mueven datos y aplicaciones a la nube, este modelo ha comenzado a ser menos eficaz a medida que rápidamente se vuelve engorroso, caro e incalable, lo que afecta significativamente al rendimiento y la eficiencia de la red de los usuarios y restringe la capacidad de la organización para adaptarse a las necesidades cambiantes. Numerosos clientes de Microsoft han informado de que hace unos años el 80 % del tráfico de red estaba en un destino interno, pero en 2020 el 80 % más del tráfico se conecta a un recurso externo basado en la nube.

La crisis del COVID-19 ha agravado el problema de requerir soluciones inmediatas para la inmensa mayoría de las organizaciones. Muchos clientes han descubierto que el modelo de VPN forzoso no es lo suficientemente escalable ni tampoco es adecuado para el 100 % de escenarios de trabajo remoto como el que necesita esta crisis. Se necesitan soluciones rápidas para que estas organizaciones sigan funcionando de forma eficiente.

Para el servicio de Office 365, Microsoft ha diseñado los requisitos de conectividad para el servicio teniendo en cuenta este problema de forma cuadrada, donde un conjunto de extremos de servicio centrado, estrechamente controlado y relativamente estático se puede optimizar de forma muy sencilla y rápida para ofrecer un alto rendimiento para los usuarios que acceden al servicio y reducir la carga en la infraestructura VPN para que pueda ser usada por el tráfico que aún lo requiere.

Office 365 clasifica los puntos de conexión necesarios para Office 365 en tres categorías: **Optimizar**, **Permitir** y **Predeterminado**. **Optimizar** los puntos de conexión es nuestra meta aquí y presenta las siguientes características:

- Son los puntos de conexión que pertenecen a Microsoft, que también se encarga de administrarlos y alojarlos en su infraestructura.
- Están dedicados a las cargas de trabajo principales de Office 365, como Exchange Online, SharePoint Online, Skype empresarial online y Microsoft Teams
- Se les ofrece IP.
- Tienen una baja tasa de cambio y un número esperado reducido (actualmente, 20 subredes IP)
- Tienen un alto volumen o son sensibles a la latencia.
- Se les puede proporcionar elementos de seguridad necesarios directamente en el servicio en lugar de en línea en la red.
- Suponen alrededor de un 70-80 % del volumen de tráfico en el servicio de Office 365.

Este conjunto de puntos de conexión de ámbito estricto se puede dividir y separar del túnel de VPN forzoso para enviarlo de forma segura directamente al servicio de Office 365 mediante la interfaz local del usuario. Esto es conocido como **túnel dividido**.

Los elementos de seguridad como DLP, protección antivirus, autenticación y control de acceso se pueden entregar de forma mucho más eficaz en estos puntos de conexión en diferentes capas del servicio. As we also divert the bulk of the traffic volume away from the VPN solution, this frees the VPN capacity up for business critical traffic that still relies on it. Asimismo, en muchos casos elimina la necesidad de usar un programa de actualización prolongado y costoso que pueda lidiar con esta nueva forma de operar.

![Detalles Tunnel configuración de VPN de división](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Figura 3: una solución de túnel dividido de VPN con excepciones de Office 365 definidas con envío directo al servicio. El resto del tráfico es forzado de vuelta a la red corporativa independientemente del destino._

Desde el punto de vista de la seguridad, Microsoft tiene una serie de características que pueden ofrecer una seguridad similar, o incluso mejor que la ofrecida por la inspección en línea de las pilas de seguridad locales. La entrada de blog del equipo de seguridad de Microsoft [Alternativas para que los profesionales de la seguridad y de TI puedan lograr controles de seguridad modernos en los escenarios de trabajo remoto actuales](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) resume claramente las características disponibles y encontrará instrucciones más detalladas en este artículo. También puede leer acerca de la implementación de Microsoft del túnel dividido de VPN en[Ejecutando en VPN: cómo Microsoft mantiene conectada a su fuerza de trabajo remota.](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

En la mayoría de los casos, esta implementación puede alcanzarse en cuestión de horas, solucionando rápidamente uno de los problemas más apremiantes de las organizaciones a la hora de extender los servicios de trabajo remoto a toda la empresa. Para obtener orientación sobre la implementación del túnel dividido de VPN, consulte[Implementación del túnel dividido de VPN para Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="related-topics"></a>Temas relacionados

[Implementación de túnel dividido de VPN en Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Optimización de rendimiento de Office 365 para usuarios de China](microsoft-365-networking-china.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Principios de conectividad de red de Office 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la red de Office 365](assessing-network-connectivity.md)

[Prueba de conectividad de Microsoft 365](https://aka.ms/netonboard)