---
title: Proteger el tráfico Teams multimedia para el túnel dividido de VPN
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
description: Proteger el tráfico Teams multimedia para el túnel dividido de VPN
ms.openlocfilehash: 0f16ed8f7f9721a79375f05f7b889bc8aab2d824
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331248"
---
# <a name="securing-teams-media-traffic-for-vpn-split-tunneling"></a>Proteger el tráfico Teams multimedia para el túnel dividido de VPN

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización Microsoft 365 usuarios remotos.

>- Para obtener información general sobre cómo usar el túnel dividido de VPN para optimizar la conectividad Microsoft 365 usuarios remotos, vea [Overview: VPN split tunneling for Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener instrucciones detalladas sobre cómo implementar el túnel dividido de VPN, consulte [Implementing VPN split tunneling for Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener una lista detallada de escenarios de túnel dividido de VPN, consulte [Escenarios de túnel dividido de VPN comunes para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener información sobre cómo configurar stream y eventos en directo en entornos VPN, consulte [Special considerations for Stream and live events in VPN environments](microsoft-365-vpn-stream-and-live-events.md).
>- Para obtener información sobre cómo optimizar Microsoft 365 el rendimiento de los inquilinos en todo el mundo para los usuarios de China, [vea optimización Microsoft 365 rendimiento para los usuarios de China](microsoft-365-networking-china.md).

Algunos Microsoft Teams pueden requerir información detallada sobre cómo funcionan los flujos de llamadas en Teams un modelo de túnel dividido y cómo se protegen las conexiones.

## <a name="configuration"></a>Configuración

Tanto para llamadas como para reuniones, siempre que las subredes IP de Optimización necesarias para medios de Teams estén correctamente en la tabla de rutas, cuando Teams llame a la función [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) para determinar qué interfaz local corresponde a la ruta que debe usar para un destino determinado, la interfaz local se devolverá para los destinos de Microsoft en los bloques IP de Microsoft enumerados anteriormente.

Algunos programas de cliente de VPN permiten la manipulación del enrutamiento en función de la dirección URL. Pero el tráfico multimedia de Teams no tiene una dirección URL asociada, por lo que el control del enrutamiento para este tráfico tiene que realizarse mediante subredes IP.

En determinadas situaciones, a menudo no relacionadas con la configuración del cliente de Teams, el tráfico multimedia atraviesa igualmente el túnel de VPN aunque se hayan dispuesto las rutas correctas. Si se produce este escenario, debe bastar con usar una regla de firewall para impedir que las subredes IP o los puertos de Teams ip no utilicen la VPN.

>[!IMPORTANT]
>Para asegurarse de que Teams tráfico multimedia se enruta Microsoft Teams través del método deseado en todos los escenarios de VPN, asegúrese de que los usuarios ejecuten una versión **de cliente 1.3.00.13565** o posterior. Esta versión incluye mejoras en la forma en que el cliente detecta las rutas de red disponibles.

El tráfico de señalización se realiza a través de HTTPS y no es tan sensible a la latencia como el tráfico multimedia y se marca como **Permitir** en los datos URL/IP y, por lo tanto, se puede enrutar de forma segura a través del cliente VPN si se desea.

>[!NOTE]
>Microsoft Edge **96 y** posteriores también admiten el túnel dividido de VPN para el tráfico punto a punto. Esto significa que los clientes pueden beneficiarse de la tunelización dividida de VPN Teams clientes web en Edge, por ejemplo. Los clientes que quieran configurarlo para sitios web que se ejecutan en Edge pueden lograrlo si toman el paso adicional de habilitar la directiva [Edge WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) .

### <a name="security"></a>Seguridad

Un argumento común para evitar túneles divididos es que es menos seguro hacerlo, es decir, cualquier tráfico que no pase por el túnel VPN no se beneficiará de cualquier esquema de cifrado que se aplique al túnel VPN y, por lo tanto, es menos seguro.

El principal argumento contra esta idea es que el tráfico multimedia ya está cifrado mediante _protocolo de transporte en tiempo real seguro (SRTP)_, un perfil del protocolo de transporte en tiempo real (RTP) que proporciona confidencialidad, autenticación y protección contra ataques de reproducciones al tráfico RTP. SRTP se basa en una clave de sesión generada al azar, que se intercambia mediante el canal de señalización protegida de TLS. Este se trata de forma detallada en [esta guía de seguridad](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online), pero la sección principal de interés es el cifrado multimedia.

El tráfico multimedia se cifra con SRTP, que usa una clave de sesión generada por un generador de números aleatorios seguros y se intercambia con el canal TLS de señalización. Además, el contenido multimedia que fluye en ambas direcciones entre el servidor de mediación y el próximo salto interno también se cifra con SRTP.

Skype Empresarial Online genera nombres de usuario o contraseñas para proteger el acceso a relés multimedia mediante _retransmisiones de uso de recorrido por NAT (TURN)_. Los relés multimedia intercambian el nombre de usuario/contraseña a través de un canal SIP protegido con TLS. Vale la pena tener en cuenta que, aunque se puede usar un túnel VPN para conectar el cliente a la red corporativa, el tráfico todavía debe fluir en su forma SRTP cuando deja la red corporativa para llegar al servicio.

En [5.1 Security Considerations for Implementers](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c) se puede encontrar información sobre cómo Teams atenúa los problemas de seguridad comunes, como los ataques de amplificación de voz o utilidades de recorrido de sesión para _NAT (STUN_).

También podrá obtener más información acerca de los controles de seguridad modernos en los escenarios de trabajo remoto en [Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto de hoy día (blog del Equipo de seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

### <a name="testing"></a>Pruebas

Una vez que la directiva está en su lugar, debe confirmar que funciona según lo esperado. Hay varias formas de probar si la ruta de acceso se ha configurado correctamente para usar la conexión a Internet local:

- Ejecute la [Microsoft 365 de conectividad que](https://aka.ms/netonboard) ejecutará pruebas de conectividad, incluidas las rutas de seguimiento como las anteriores. También estamos agregando pruebas de VPN a esta herramienta que también debe proporcionar información adicional.

- Un **tracert simple** a un punto de conexión dentro del ámbito del túnel dividido debe mostrar la ruta de acceso tomada, por ejemplo:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  A continuación, debe ver una ruta de acceso a través del ISP local a este punto de conexión que debe resolverse en una DIRECCIÓN IP en los intervalos de Teams que hemos configurado para el túnel dividido.

- Realice una captura de red con una herramienta como Wireshark. Filtre por UDP durante una llamada y debería ver el tráfico que fluye a una dirección IP en el intervalo **Optimizar** de Teams. Si el túnel VPN se usa para este tráfico, el tráfico multimedia no será visible en el seguimiento.

## <a name="additional-support-logs"></a>Registros de soporte adicional

Si necesita más datos para solucionar problemas o bien asistencia del soporte técnico de Microsoft, la obtención de la siguiente información le permite acelerar la búsqueda de una solución. El TSS de microsoft Windows conjunto de herramientas de script de **troubleShooting universal** basado en CMD puede ayudarle a recopilar los registros relevantes de una manera sencilla. La herramienta y las instrucciones de uso se pueden encontrar en <https://aka.ms/TssTools>.

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Implementación de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[Escenarios comunes de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365 optimización del rendimiento para usuarios de China](microsoft-365-networking-china.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Microsoft 365 de red y rendimiento](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
