---
title: 'Conexión de red (en la nube): el punto de vista de un arquitecto'
description: Obtenga información sobre cómo optimizar la red para la conectividad en la nube evitando los problemas más comunes.
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 8b999337f18f4de714dcb9746b49d4abd171072d
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986518"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Conexión de red (en la nube): el punto de vista de un arquitecto

En este artículo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), arquitecto de cumplimiento de seguridad & de Microsoft, describe cómo optimizar la red para la conectividad en la nube evitando los problemas más comunes.

## <a name="about-the-author"></a>Acerca del autor

![Foto de Ed Fisher.](../media/solutions-architecture-center/ed-fisher-networking.jpg)

Actualmente soy un especialista técnico principal en nuestro equipo de minoristas y bienes de consumo, centrándome en seguridad & cumplimiento. He trabajado con clientes que se mudan a Office 365 durante los últimos diez años. He trabajado con tiendas más pequeñas con un puñado de ubicaciones para agencias gubernamentales y empresas con millones de usuarios distribuidos por todo el mundo, y muchos otros clientes en el medio, con la mayoría con decenas de miles de usuarios, varias ubicaciones en varias partes del mundo, la necesidad de un mayor grado de seguridad y una gran cantidad de requisitos de cumplimiento. He ayudado a cientos de empresas y millones de usuarios a migrar a la nube de forma segura y segura.

Con una experiencia en los últimos 25 años que incluye la seguridad, la infraestructura y la ingeniería de red, y haber movido a dos de mis empleadores anteriores a Office 365 antes de unirse a Microsoft, he estado de su lado muchas veces, y recuerde lo que es eso. Aunque ninguno de los dos clientes es nunca el mismo, la mayoría tiene necesidades similares y, al consumir un servicio estandarizado como cualquier plataforma SaaS o PaaS, los mejores enfoques tienden a ser los mismos.

## <a name="its-not-the-network--its-how-youre-misusing-it"></a>No es la red, es cómo la usas (mal).

No importa cuántas veces se produzca, nunca deja de sorprenderme cómo los equipos de seguridad *creativos* y los equipos de redes intentan obtener información sobre cómo creen que deben conectarse a los servicios en la nube de Microsoft. Siempre hay alguna directiva de seguridad, estándar de cumplimiento o mejor manera en la que insisten en usar, sin estar dispuestos a participar en una conversación sobre lo que están intentando lograr o *cómo* hay formas mejores, más fáciles, más rentables y más eficaces de hacerlo.

Cuando este tipo de cosas se escalan a mí, normalmente estoy dispuesto a aceptar el desafío y guiarlos a través de los cánones y los por qué y llevarlos a donde necesitan estar. Pero si estoy siendo completamente franco, tengo que compartir que a veces quiero dejar que hagan lo que quieran, y volver a decir que te lo dije cuando finalmente conceden que no funciona. Puede que quiera hacerlo a veces, pero *no* lo hago. Lo que hago es intentar explicar todo lo que voy a incluir en este post. Independientemente de su rol, si su organización quiere usar los servicios en la nube de Microsoft, probablemente haya algo de sabiduría en lo siguiente que puede ayudarle.

## <a name="guiding-principles"></a>Principios rectores

Comencemos con algunas reglas básicas sobre lo que estamos haciendo aquí. Estamos analizando cómo conectarse de forma segura a los servicios en la nube para garantizar la complejidad mínima y el máximo rendimiento, a la vez que se mantiene la seguridad real. Nada de lo que sigue es contrario a nada de eso, incluso si usted o su cliente no podrán usar su servidor proxy favorito para todo.

- **Sólo porque puedas, no significa que debas**: O parafrasear al Dr. Ian Malcolm de la película Jurassic Park "... Sí, sí, pero su equipo de seguridad estaba tan preocupado por si podían o no que no se detuvieran a pensar si deberían".
- **La seguridad no significa complejidad**: no es más seguro solo porque gasta más dinero, enruta a través de más dispositivos o hace clic en más botones.
- **Office 365 se accede a través de Internet**: Pero eso no es lo mismo que Office 365 es Internet. Es un servicio SaaS administrado por Microsoft y administrado por usted. A diferencia de los sitios web que visita en Internet, realmente puede echar un vistazo detrás de la cortina, y puede aplicar los controles que necesita para cumplir sus directivas y sus estándares de cumplimiento, siempre y cuando entienda que, aunque puede cumplir sus objetivos, puede que solo tenga que hacerlo de una manera diferente.
- **Los puntos de interrupción son incorrectos, los saltos localizados son buenos**: todo el mundo siempre quiere revertir todo su tráfico de Internet para todos sus usuarios a algún punto central, normalmente para que puedan supervisarlo y aplicar la directiva, pero a menudo porque es más barato que aprovisionar el acceso a Internet en todas sus ubicaciones, o es simplemente cómo lo hacen. Pero esos puntos de atragantamiento son exactamente eso... puntos donde se atasque el tráfico. No hay nada de malo en impedir que los usuarios naveguen a Instagram o transmita vídeos de gatos, pero no traten el tráfico de aplicaciones empresariales críticas de la misma manera.
- **Si dns no está contento, no es nada feliz**: la red mejor diseñada puede ser hamstrung por DNS deficiente, ya sea mediante la repetición de solicitudes a servidores en otras áreas del mundo o el uso de los servidores DNS de su ISP u otros servidores DNS públicos que almacenan en caché la información de resolución DNS.
- **Solo porque así es como solía hacerlo, no significa que así sea como debería hacerlo ahora**: la tecnología cambia constantemente y Office 365 no es una excepción. La aplicación de medidas de seguridad desarrolladas e implementadas para servicios locales o para controlar la navegación web no va a proporcionar el mismo nivel de seguridad y puede tener un impacto negativo significativo en el rendimiento.
- **Office 365 se ha creado para que se pueda acceder a través de Internet**: en pocas palabras. No importa lo que quieras hacer entre tus usuarios y tu perímetro, el tráfico sigue a través de Internet una vez que sale de la red y antes de que llegue a la nuestra. Incluso si usa Azure ExpressRoute para enrutar algún tráfico confidencial de latencia desde la red directamente a la nuestra, la conectividad a Internet es absolutamente necesaria. Acéptelo. No lo escalones.

## <a name="where-bad-choices-are-often-made"></a>Donde a menudo se toman decisiones incorrectas

Aunque hay muchos lugares donde se toman decisiones incorrectas en nombre de la seguridad, estos son los que encuentro con más frecuencia con los clientes. Muchas conversaciones con los clientes implican todas ellas a la vez.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes en el perímetro

Muy pocos clientes están implementando entornos de campo verde y tienen años de experiencia con cómo funcionan sus usuarios y cómo es su salida de Internet. Tanto si los clientes tienen servidores proxy como si permiten el acceso directo y simplemente el tráfico saliente de NAT, lo han estado haciendo durante años y no tienen en cuenta cuánto más van a empezar a bombear a través de su perímetro, ya que mueven tradicionalmente las aplicaciones internas a la nube.

El ancho de banda siempre es un problema, pero es posible que los dispositivos NAT no tengan suficiente potencia para controlar el aumento de la carga y puedan empezar a cerrar prematuramente las conexiones para liberar recursos. La mayoría del software cliente que se conecta a Office 365 espera conexiones persistentes y un usuario que usa completamente Office 365 puede tener 32 o más conexiones simultáneas. Si el dispositivo NAT los está quitando prematuramente, esas aplicaciones pueden dejar de responder cuando intentan usar las conexiones que ya no están allí. Cuando se dan por vencieron e intentan establecer nuevas conexiones, ponen aún más carga en el engranaje de red.

### <a name="localized-breakout"></a>Interrupción localizada

Todo lo demás de esta lista se reduce a una cosa: salir de la red y conectarse a la nuestra lo más rápido posible. La devolución del tráfico de los usuarios a un punto de salida central, especialmente cuando ese punto de salida está en otra región que la de los usuarios, presenta una latencia innecesaria y afecta tanto a la experiencia del cliente como a las velocidades de descarga. Microsoft tiene puntos de presencia en todo el mundo con front-end para todos nuestros servicios y emparejamiento establecidos con prácticamente todos los ISP principales, por lo que enrutar el tráfico de los usuarios *localmente* garantiza que entra en nuestra red rápidamente con una latencia mínima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>El tráfico de resolución DNS debe seguir la ruta de salida de Internet

Por supuesto, para que un cliente encuentre cualquier punto de conexión, debe usar DNS. Los servidores DNS de Microsoft evalúan el origen de las solicitudes DNS para garantizar que se devuelve la respuesta que es, en términos de Internet, más cercana al origen de la solicitud. Asegúrese de que el DNS está configurado para que las solicitudes de resolución de nombres salgan de la misma ruta que el tráfico de los usuarios, para no darles salida local sino a un punto de conexión de otra región. Esto significa permitir que los servidores DNS locales "vayan a la raíz" en lugar de reenviarlos a servidores DNS en centros de datos remotos. Además, tenga cuidado con los servicios DNS públicos y privados, que pueden almacenar en caché los resultados de una parte del mundo y servirlos para las solicitudes de otras partes del mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Para proxy o no para proxy, esa es la pregunta

Una de las primeras cosas que hay que tener en cuenta es si se van a proxy las conexiones de los usuarios a Office 365. Que uno es fácil; no proxy. Office 365 se accede a través de Internet, pero no es Internet. Es una extensión de los servicios principales y debe tratarse como tal. Cualquier cosa que quiera que haga un proxy, como DLP o antimalware o inspección de contenido, ya está disponible en el servicio y se puede usar a escala y sin necesidad de descifrar las conexiones cifradas con TLS. Pero si realmente desea proxy de tráfico que no se puede controlar de otro modo, preste atención a nuestra guía en [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) y las categorías de tráfico en [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md). Tenemos tres categorías de tráfico para Office 365. Optimizar y permitir realmente debe ir directo y omitir el proxy. El valor predeterminado se puede proxy. Los detalles están en esos documentos... léelas.

La mayoría de los clientes que insisten en usar un proxy, cuando realmente miran lo que están haciendo, se dan cuenta de que cuando el cliente realiza una solicitud HTTP CONNECT al proxy, el proxy es ahora solo un enrutador adicional costoso. Los protocolos en uso, como MAPI y RTC, ni siquiera son protocolos que los servidores proxy web entienden, por lo que incluso con el descifrado de TLS no se obtiene realmente ninguna seguridad adicional. Obtiene una latencia adicional. Para obtener [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) más información sobre esto, incluidas las categorías Optimizar, Permitir y Predeterminado para el tráfico de Microsoft 365.

Por último, tenga en cuenta el impacto general para el proxy y su respuesta correspondiente para abordar ese impacto. A medida que se realizan más y más conexiones a través del proxy, puede reducir el factor de escala TCP para que no tenga que almacenar en búfer tanto tráfico. He visto a los clientes donde sus servidores proxy estaban tan sobrecargados que estaban usando un factor de escala de 0. Dado que factor de escala es un valor exponencial y nos gusta usar 8, cada reducción en el valor del factor de escala es un gran impacto negativo en el rendimiento.

Inspección tls significa seguridad! ¡Pero en realidad no! Muchos clientes con servidores proxy quieren usarlos para inspeccionar todo el tráfico, lo que significa que TLS "interrumpe e inspecciona". Cuando lo hace para un sitio web al que se accede a través de HTTPS (no obstante los problemas de privacidad), es posible que el proxy tenga que hacerlo durante 10 o incluso 20 flujos simultáneos durante unos pocos cientos de milisegundos. Si hay una descarga grande o tal vez un vídeo implicado, una o varias de esas conexiones pueden durar mucho más, pero en general, la mayoría de esas conexiones establecen, transfieren y cierran muy rápidamente. Al interrumpir e inspeccionar significa que el proxy debe hacer el doble del trabajo. Para cada conexión del cliente al proxy, el proxy también debe realizar una conexión independiente con el punto de conexión. Por lo tanto, 1 se convierte en 2, 2 se convierte en 4, 32 se convierte en 64...ver a dónde voy? Probablemente ha dimensionado la solución de proxy perfectamente para la navegación web típica, pero cuando intenta hacer lo mismo con las conexiones de cliente a Office 365, el número de conexiones simultáneas de larga duración puede ser de magnitud mayor que la que ha dimensionado.

### <a name="streaming-isnt-important-except-that-it-is"></a>El streaming no es importante, salvo que *es*

Los únicos servicios de Office 365 que usan UDP son Skype (que pronto se retirará) y Microsoft Teams. Teams usa UDP para el tráfico de streaming, incluido el uso compartido de audio, vídeo y presentación. El tráfico de streaming está en directo, como cuando se tiene una reunión en línea con voz, vídeo y presentación de barajas o la realización de demostraciones. Estos usan UDP porque si los paquetes se quitan o llegan fuera de orden, es prácticamente imperceptible para el usuario y la secuencia puede continuar.

Cuando no permite el tráfico UDP saliente de los clientes al servicio, pueden volver a usar TCP. Pero si se quita un paquete TCP, *todo se detiene* hasta que expira el tiempo de espera de retransmisión (RTO) y se puede retransmitir el paquete que falta. Si un paquete llega fuera de orden, todo se detiene hasta que llegan los otros paquetes y se pueden volver a ensamblar en orden. Ambos provocan problemas perceptibles en el audio (¿recuerdas Max Headroom?) y vídeo (has hecho clic en algo... oh, ahí está) y conducir a un rendimiento deficiente y una mala experiencia de usuario. ¿Y recuerdas lo que puse anteriormente sobre los servidores proxy? Cuando se fuerza a un cliente de Teams a usar un proxy, se fuerza a usar TCP. Por lo tanto, ahora está causando impactos negativos en el rendimiento dos veces.

### <a name="split-tunneling-may-seem-scary"></a>La tunelización dividida puede parecer aterradora

Pero no lo es. Todas las conexiones a Office 365 se realizan a través de TLS. Hemos estado ofreciendo TLS 1.2 durante bastante tiempo y pronto deshabilitaremos las versiones anteriores porque los clientes heredados todavía las usan y eso es un riesgo.

Forzar una conexión TLS, o 32 de ellas, para pasar por una VPN antes de ir al servicio no agrega seguridad. Agrega latencia y reduce el rendimiento general. En algunas soluciones de VPN, incluso obliga a UDP a tunelizar a través de TCP, lo que de nuevo tendrá un impacto muy negativo en el tráfico de streaming. Y, a menos que realice la inspección de TLS, no hay ningún inconveniente. Un tema muy común entre los clientes, ahora que la mayoría de su personal es remota, es que están viendo impactos significativos en el ancho de banda y el rendimiento al hacer que todos sus usuarios se conecten mediante una VPN, en lugar de configurar la tunelización dividida para el acceso a [la categoría Optimize Office 365 puntos de conexión](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).

Es una solución fácil de hacer tunelización dividida y es una que debe hacer. Para obtener más información, asegúrese de revisar [Optimizar la conectividad Office 365 para usuarios remotos mediante la tunelización dividida de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="the-sins-of-the-past"></a>Los pecados del pasado

Muchas veces, la razón por la que se toman malas decisiones procede de una combinación de (1) no saber cómo funciona el servicio, (2) intentar cumplir las directivas de la empresa que se escribieron antes de adoptar la nube y (3) equipos de seguridad que pueden no estar fácilmente convencidos de que hay más de una manera de lograr sus objetivos. Esperemos que lo anterior, y los vínculos siguientes, ayuden con el primero. Es posible que sea necesario el patrocinio ejecutivo para superar el segundo. Abordar los objetivos de las directivas de seguridad, en lugar de sus métodos, ayuda con el tercero. Desde el acceso condicional a la moderación del contenido, DLP a la protección de la información, la validación de puntos de conexión a las amenazas de día cero: cualquier objetivo final que una directiva de seguridad razonable pueda tener se puede lograr con lo que está disponible en Office 365 y sin ninguna dependencia del engranaje de red local, los túneles VPN forzados y la interrupción e inspección de TLS.

Otras veces, el hardware que se ha dimensionado y comprado antes de que la organización empezara a moverse a la nube simplemente no se puede escalar verticalmente para controlar los nuevos patrones de tráfico y cargas. Si realmente debe enrutar todo el tráfico a través de un único punto de salida o proxy, esté preparado para actualizar el equipo de red y el ancho de banda en consecuencia. Supervise cuidadosamente el uso en ambos, ya que la experiencia no disminuirá lentamente a medida que más usuarios se incorporen. Todo estará bien hasta que se alcance el punto de inflexión, entonces todo el mundo sufre.

## <a name="exceptions-to-the-rules"></a>Excepciones a las reglas

Si su organización requiere [restricciones de inquilino](/azure/active-directory/manage-apps/tenant-restrictions), tendrá que usar un proxy con interrupción de TLS e inspeccionar para forzar el tráfico a través del proxy, pero no es necesario forzar todo el tráfico a través de él.  No es una propuesta de todo o nada, así que preste atención a lo que necesita modificar el proxy.

Si va a permitir la tunelización dividida, pero también usa un proxy para el tráfico web general, asegúrese de que el archivo PAC define lo que debe ir directamente, así como cómo define el tráfico interesante para lo que pasa a través del túnel VPN. Ofrecemos archivos PAC de ejemplo en [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) que harán que esto sea más fácil de administrar.

## <a name="conclusion"></a>Conclusión

Decenas de miles de organizaciones, incluyendo casi todas las fortune 500, usan Office 365 todos los días para sus funciones críticas. Lo hacen de forma segura, y lo hacen a través de Internet.

Independientemente de los objetivos de seguridad que tenga en juego, hay maneras de lograrlos que no requieren conexiones VPN, servidores proxy, interrupción e inspección de TLS o salida centralizada de Internet para sacar el tráfico de los usuarios de la red y continuar con el nuestro lo más rápido posible, lo que proporciona el mejor rendimiento, independientemente de si la red es la sede central de la empresa,  una oficina remota o ese usuario que trabaja en casa. Nuestra guía se basa en cómo se crean los servicios de Office 365 y para garantizar una experiencia de usuario segura y eficaz.

## <a name="further-reading"></a>Lectura adicional

[Principios de conectividad de red de Office 365](../enterprise/microsoft-365-network-connectivity-principles.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Administrar puntos de conexión de Office 365](../enterprise/managing-office-365-endpoints.md)

[Dirección IP de Office 365 y servicio web de URL](../enterprise/microsoft-365-ip-web-service.md)

[Evaluar la red de Office 365](../enterprise/assessing-network-connectivity.md)

[Red de Office 365 y ajuste de rendimiento](../enterprise/network-planning-and-performance.md)

[Evaluar la conectividad de red de Office 365](../enterprise/assessing-network-connectivity.md)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](../enterprise/performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](../enterprise/performance-troubleshooting-plan.md)

[Redes de entrega de contenido](../enterprise/content-delivery-networks.md)

[Prueba de conectividad de Microsoft 365](https://connectivity.office.com/)

[Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de redes de Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 conectividad para usuarios remotos mediante la tunelización dividida de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md)
