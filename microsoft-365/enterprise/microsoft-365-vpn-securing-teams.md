---
title: Protección del tráfico multimedia Teams para la tunelización dividida VPN
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Protección del tráfico multimedia Teams para la tunelización dividida VPN
ms.openlocfilehash: fc37f945b95aedfc837063ceb028f48a05a1d48b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68170253"
---
# <a name="securing-teams-media-traffic-for-vpn-split-tunneling"></a>Protección del tráfico multimedia Teams para la tunelización dividida VPN

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización de Microsoft 365 para usuarios remotos.

>- Para obtener información general sobre el uso de la tunelización dividida de VPN para optimizar la conectividad de Microsoft 365 para usuarios remotos, consulte [Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener instrucciones detalladas sobre la implementación de la tunelización dividida de VPN, consulte [Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener una lista detallada de escenarios de tunelización dividida de VPN, consulte [Escenarios comunes de tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener información sobre cómo configurar stream y eventos en directo en entornos VPN, consulte [Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md).
>- Para obtener información sobre cómo optimizar el rendimiento de los inquilinos de Microsoft 365 en todo el mundo para los usuarios de China, consulte [Optimización del rendimiento de Microsoft 365 para los usuarios de China](microsoft-365-networking-china.md).

Algunos administradores de Microsoft Teams pueden requerir información detallada sobre cómo funcionan los flujos de llamadas en Teams mediante un modelo de tunelización dividida y cómo se protegen las conexiones.

## <a name="configuration"></a>Configuración

En el caso de las llamadas y reuniones, siempre y cuando las subredes IP necesarias para los medios de Teams estén correctamente implementadas en la tabla de rutas, cuando Teams llame a la función [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) para determinar qué interfaz local corresponde a la ruta que debe usar para un destino determinado, se devolverá la interfaz local para los destinos de Microsoft en los bloques IP de Microsoft enumerados anteriormente.

Algunos programas de cliente de VPN permiten la manipulación del enrutamiento en función de la dirección URL. Pero el tráfico multimedia de Teams no tiene una dirección URL asociada, por lo que el control del enrutamiento para este tráfico tiene que realizarse mediante subredes IP.

En determinadas situaciones, a menudo no relacionadas con la configuración del cliente de Teams, el tráfico multimedia atraviesa igualmente el túnel de VPN aunque se hayan dispuesto las rutas correctas. Si encuentra este escenario, debe bastar con usar una regla de firewall para impedir que las subredes o puertos IP de Teams usen la VPN.

>[!IMPORTANT]
>Para asegurarse de que el tráfico multimedia de Teams se enruta a través del método deseado en todos los escenarios de VPN, asegúrese de que los usuarios ejecutan la versión de cliente de Microsoft Teams **1.3.00.13565** o posterior. Esta versión incluye mejoras en la forma en que el cliente detecta las rutas de acceso de red disponibles.

El tráfico de señalización se realiza a través de HTTPS y no es tan sensible a la latencia como el tráfico multimedia y se marca como **Permitir** en los datos de DIRECCIÓN URL/IP y, por tanto, se puede enrutar de forma segura a través del cliente VPN si lo desea.

>[!NOTE]
>Microsoft Edge **96 y versiones posteriores** también admiten la tunelización dividida de VPN para el tráfico punto a punto. Esto significa que los clientes pueden beneficiarse de la tunelización dividida de VPN para clientes web de Teams en Edge, por ejemplo. Los clientes que quieran configurarlo para sitios web que se ejecutan en Edge pueden lograrlo si toman el paso adicional de deshabilitar la directiva [Edge WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) .

### <a name="security"></a>Seguridad

Un argumento común para evitar túneles divididos es que es menos seguro hacerlo, es decir, Cualquier tráfico que no pase por el túnel VPN no se beneficiará de cualquier esquema de cifrado que se aplique al túnel VPN y, por tanto, sea menos seguro.

El principal argumento contra esta idea es que el tráfico multimedia ya está cifrado mediante _protocolo de transporte en tiempo real seguro (SRTP)_, un perfil del protocolo de transporte en tiempo real (RTP) que proporciona confidencialidad, autenticación y protección contra ataques de reproducciones al tráfico RTP. SRTP se basa en una clave de sesión generada al azar, que se intercambia mediante el canal de señalización protegida de TLS. Este se trata de forma detallada en [esta guía de seguridad](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online), pero la sección principal de interés es el cifrado multimedia.

El tráfico multimedia se cifra con SRTP, que usa una clave de sesión generada por un generador de números aleatorios seguros y se intercambia con el canal TLS de señalización. Además, el contenido multimedia que fluye en ambas direcciones entre el servidor de mediación y el próximo salto interno también se cifra con SRTP.

Skype Empresarial Online genera nombres de usuario o contraseñas para proteger el acceso a relés multimedia mediante _retransmisiones de uso de recorrido por NAT (TURN)_. Los relés multimedia intercambian el nombre de usuario/contraseña a través de un canal SIP protegido con TLS. Vale la pena señalar que, aunque se pueda usar un túnel VPN para conectar el cliente a la red corporativa, el tráfico todavía debe fluir en su forma SRTP cuando sale de la red corporativa para llegar al servicio.

Puede encontrar información sobre cómo Teams mitiga problemas comunes de seguridad, como las utilidades de voz o de recorrido de sesión para ataques de amplificación _NAT (STUN),_ en [Consideraciones de seguridad 5.1 para los implementadores](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c).

También podrá obtener más información acerca de los controles de seguridad modernos en los escenarios de trabajo remoto en [Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto de hoy día (blog del Equipo de seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

### <a name="testing"></a>Pruebas

Una vez implementada la directiva, debe confirmar que funciona según lo esperado. Hay varias formas de probar si la ruta de acceso se ha configurado correctamente para usar la conexión a Internet local:

- Ejecute la [prueba de conectividad de Microsoft 365](https://aka.ms/netonboard) que ejecutará pruebas de conectividad para usted, incluidas las rutas de seguimiento como se mencionó anteriormente. También vamos a agregar pruebas VPN a esta herramienta que también debe proporcionar información adicional.

- Un **seguimiento** simple a un punto de conexión dentro del ámbito del túnel dividido debe mostrar la ruta de acceso tomada, por ejemplo:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  A continuación, debería ver una ruta de acceso a través del ISP local a este punto de conexión que debe resolverse en una dirección IP en los intervalos de Teams que hemos configurado para la tunelización dividida.

- Realice una captura de red con una herramienta como Wireshark. Filtre por UDP durante una llamada y debería ver el tráfico que fluye a una dirección IP en el intervalo **Optimizar** de Teams. Si el túnel VPN se usa para este tráfico, el tráfico multimedia no será visible en el seguimiento.

## <a name="additional-support-logs"></a>Registros de soporte adicional

Si necesita más datos para solucionar problemas o bien asistencia del soporte técnico de Microsoft, la obtención de la siguiente información le permite acelerar la búsqueda de una solución. El conjunto de herramientas **TSS Windows CMD universal de Microsoft TroubleShooting Script** puede ayudarle a recopilar los registros pertinentes de forma sencilla. La herramienta y las instrucciones de uso se pueden encontrar en <https://aka.ms/TssTools>.

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[Escenarios comunes de tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md)

[Optimización del rendimiento de Microsoft 365 para usuarios de China](microsoft-365-networking-china.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Optimización de rendimiento y red de Microsoft 365](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
