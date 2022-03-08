---
title: Escenarios comunes de túnel dividido de VPN para Microsoft 365
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
f1.keywords:
- NOCSH
description: Escenarios comunes de túnel dividido de VPN para Microsoft 365
ms.openlocfilehash: 26f4cf10de3282c5257592a26ea61d073a0d3cd4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331326"
---
# <a name="common-vpn-split-tunneling-scenarios-for-microsoft-365"></a>Escenarios comunes de túnel dividido de VPN para Microsoft 365

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización Microsoft 365 usuarios remotos.

>- Para obtener información general sobre cómo usar el túnel dividido de VPN para optimizar la conectividad Microsoft 365 usuarios remotos, vea [Overview: VPN split tunneling for Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener instrucciones detalladas sobre cómo implementar el túnel dividido de VPN, consulte [Implementing VPN split tunneling for Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener instrucciones sobre cómo proteger el Teams de medios en entornos de túnel dividido de VPN, consulte [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md).
>- Para obtener información sobre cómo configurar stream y eventos en directo en entornos VPN, consulte [Special considerations for Stream and live events in VPN environments](microsoft-365-vpn-stream-and-live-events.md).
>- Para obtener información sobre cómo optimizar Microsoft 365 el rendimiento de los inquilinos en todo el mundo para los usuarios de China, [vea optimización Microsoft 365 rendimiento para los usuarios de China](microsoft-365-networking-china.md).

En la lista siguiente, verás los escenarios de VPN más comunes que se ven en entornos empresariales. La mayoría de los clientes utiliza el modelo 1 de forma tradicional (túnel forzado de VPN). Esta sección le ayudará a realizar una transición rápida y segura al modelo **2**, que se puede lograr con relativamente poco esfuerzo y tiene enormes ventajas para el rendimiento de la red y la experiencia del usuario.

| Model | Descripción |
| --- | --- |
| [1. Túnel forzado de VPN](#1-vpn-forced-tunnel) | El 100 % del tráfico entra en el túnel VPN, incluidos los entornos locales, Internet y todo O365/M365 |
| [2. Túnel forzado de VPN con unas pocas excepciones](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | El túnel de VPN se usa de forma predeterminada (la ruta predeterminada apunta a la VPN), con pocos escenarios de exención especialmente importantes que se pueden dirigir directamente |
| [3. Túnel forzado de VPN con muchas excepciones](#3-vpn-forced-tunnel-with-broad-exceptions) | El túnel VPN se usa de forma predeterminada (la ruta predeterminada apunta a VPN), con amplias excepciones que pueden ir directamente (como todas las Microsoft 365, All Salesforce, All Zoom) |
| [4. Túnel de VPN selectivo](#4-vpn-selective-tunnel) | El túnel VPN solo se usa para los servicios basados en corpnet. La ruta predeterminada (Internet y todos los servicios basados en Internet) va directamente. |
| [5. No VPN](#5-no-vpn) | Variación de #2. En lugar de vpn heredada, todos los servicios corpnet se publican a través de enfoques de seguridad modernos (como Zscaler ZPA, Azure Active Directory (Azure AD) Proxy/MCAS, etc.) |

## <a name="1-vpn-forced-tunnel"></a>1. Túnel forzado de VPN

El escenario de inicio más común para la mayoría de los clientes empresariales. Se usa una VPN forzada, lo que significa que el 100 % del tráfico se dirige a la red corporativa independientemente de si el extremo reside dentro de la red corporativa o no. Cualquier tráfico externo (Internet) enlazado, como Microsoft 365 o navegación por Internet, se vuelve a anclar de nuevo fuera del equipamiento de seguridad local, como servidores proxy. En el actual entorno en el que casi el 100 % de los usuarios trabajan de forma remota, este modelo pone una gran carga en la infraestructura VPN y es probable que dificulte significativamente el rendimiento de todo el tráfico corporativo y, por lo tanto, la empresa funcione de forma eficaz en un momento de crisis.

![VPN forced Tunnel model 1.](../media/vpn-split-tunneling/vpn-model-1.png)

## <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. Túnel forzado de VPN con unas pocas excepciones de confianza

Significativamente más eficaz para que una empresa funcione bajo. Este modelo permite que algunos puntos de conexión controlados y definidos que son sensibles a la alta carga y la latencia omitan el túnel VPN y vayan directamente al servicio Microsoft 365 cliente. Esto mejora significativamente el rendimiento de los servicios descargados y también disminuye la carga en la infraestructura VPN, lo que permite que los elementos que aún lo requieran funcionen con menor contención de recursos. Este modelo se centra en ayudar con la transición a, ya que permite realizar acciones sencillas y definidas rápidamente con numerosos resultados positivos.

![Split Tunnel modelo 2 de VPN.](../media/vpn-split-tunneling/vpn-model-2.png)

## <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. Túnel forzado de VPN con muchas excepciones

Amplía el ámbito del modelo 2. En lugar de enviar un pequeño grupo de puntos de conexión definidos directamente, en su lugar envía todo el tráfico directamente a servicios de confianza como Microsoft 365 y SalesForce. Esto reduce aún más la carga en la infraestructura VPN corporativa y mejora el rendimiento de los servicios definidos. Dado que es probable que este modelo tarde más tiempo en evaluar la viabilidad de e implementarlo, es probable que sea un paso que se pueda realizar iterativamente en una fecha posterior una vez que el modelo dos se haya implementado correctamente.

![Split Tunnel modelo 3 de VPN.](../media/vpn-split-tunneling/vpn-model-3.png)

## <a name="4-vpn-selective-tunnel"></a>4. Túnel de VPN selectivo

Invierte el tercer modelo en que solo el tráfico identificado como tener una dirección IP corporativa se envía por el túnel VPN y, por lo tanto, la ruta de acceso a Internet es la ruta predeterminada para todo lo demás. Este modelo requiere que la organización se encuentre en una fase avanzada de implementación de [Confianza cero](https://www.microsoft.com/security/zero-trust?rtc=1) para poder implementar el modelo de forma segura. Debe tenerse en cuenta que este modelo o alguna variación del mismo probablemente se convertirá en el valor predeterminado necesario con el tiempo a medida que más servicios se alejan de la red corporativa y de la nube.

Microsoft usa este modelo internamente. Encontrará más información sobre la implementación de túnel dividido de VPN de Microsoft en [Running on VPN: How Microsoft is keeping its remote workforce connected](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

![Split Tunnel modelo 4 de VPN.](../media/vpn-split-tunneling/vpn-model-4.png)

## <a name="5-no-vpn"></a>5. No VPN

Una versión más avanzada del modelo número 2, en la que cualquier servicio interno se publica a través de un enfoque de seguridad moderno o una solución SDWAN como Azure AD Proxy, Defender para aplicaciones en la nube, Zscaler ZPA, etc.

![Split Tunnel modelo 5 de VPN.](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Implementación de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

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
