---
title: 'Creación de redes (en la nube): punto de vista de un arquitecto'
description: Aprenda a optimizar la red para la conectividad en la nube evitando los problemas más comunes.
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904641"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Creación de redes (en la nube): punto de vista de un arquitecto

En este artículo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect en Microsoft, describe cómo optimizar la red para la conectividad en la nube evitando los problemas más comunes. 

## <a name="about-the-author"></a>Acerca del autor

![Foto de Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Actualmente soy un especialista técnico principal en la región sudoriental centrado en la seguridad y & cumplimiento. He trabajado con clientes que se han mudado a Office 365 durante los últimos 10 años. He trabajado con tiendas más pequeñas con un puñado de ubicaciones para agencias gubernamentales y empresas con millones de usuarios distribuidos por todo el mundo, y muchos otros clientes en el medio, con la mayoría de decenas de miles de usuarios, varias ubicaciones en varias partes del mundo, la necesidad de un mayor grado de seguridad y una gran variedad de requisitos de cumplimiento. He ayudado a cientos de empresas y millones de usuarios a moverse a la nube de forma segura y segura.

Con un fondo en los últimos 25 años que incluye seguridad, infraestructura e ingeniería de red, y después de haber movido dos de mis anteriores empleadores a Office 365 antes de unirse a Microsoft, he estado muchas veces de su lado de la tabla y me acuerdo de cómo es eso. Aunque no hay dos clientes iguales, la mayoría tiene necesidades similares y al consumir un servicio estandarizado como cualquier plataforma SaaS o PaaS, los mejores enfoques tienden a ser los mismos.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>No es la red, es como la usas (mal)

No importa cuántas veces suceda, nunca deja  de sorprenderme cómo los equipos creativos de seguridad y los equipos de redes intentan llegar con la forma en que creen que deben conectarse a los servicios en la nube de Microsoft. Siempre hay alguna directiva de seguridad, estándar de cumplimiento o mejor manera en que insisten en el uso,  sin estar dispuestos a participar en una conversación sobre lo que están intentando lograr o cómo son mejores, más fáciles, más rentables y formas más eficaces de hacerlo.

When this sort of thing is escalated to me, I'm usually willing to take the challenge and walk them through the how's and the why's and get them to where they need to be. Pero si estoy siendo completamente franco, tengo que compartir que a veces solo quiero dejarles hacer lo que quieran y volver a decir que se lo he dicho cuando finalmente conceden que no funciona. Es posible que quiera hacerlo a veces, pero *no*. Lo que hago es intentar explicar todo lo que voy a incluir en esta publicación. Independientemente de su rol, si su organización quiere usar los servicios en la nube de Microsoft, probablemente haya cierta prudencia en lo que sigue que puede ayudarle.

## <a name="guiding-principles"></a>Principios de guía

Empecemos con algunas reglas básicas en torno a lo que estamos haciendo aquí. Estamos analizando cómo conectarse de forma segura a los servicios en la nube para garantizar la complejidad mínima y el rendimiento máximo, manteniendo al mismo tiempo la seguridad real. Nada de lo que sigue es contrario a nada de eso, incluso si usted, o su cliente, no podrá usar su servidor proxy favorito para todo.

- **Simplemente porque pueda, no** significa que deba : O parafraseando al Dr. Ian Malcolm de la película Parque Jurásico "... Sí, sí, pero el equipo de seguridad estaba tan preocupado por saber si podían o no que no se detuvieran a pensar si deberían hacerlo".
- **La seguridad no significa complejidad:** no es más seguro solo porque se invierte más dinero, se enruta a través de más dispositivos o se hacen clic en más botones.
- **Office 365 se tiene acceso a** través de Internet: pero no es lo mismo que Office 365 internet. Es un servicio SaaS administrado por Microsoft y administrado por usted. A diferencia de los sitios web que visita en Internet, realmente puede echar un vistazo detrás de la cortina y puede aplicar los controles que necesita para cumplir sus directivas y sus estándares de cumplimiento, siempre que comprenda que, aunque puede cumplir sus objetivos, puede que solo tenga que hacerlo de una manera diferente.
- Los puntos de congestión son malos, las **rupturas localizadas** son buenas: todos siempre quieren devolver todo el tráfico de Internet de todos sus usuarios a algún punto central, normalmente para que puedan supervisarlo y aplicar la directiva, pero a menudo porque es más económico que aprovisionar acceso a Internet en todas sus ubicaciones, o es justo cómo lo hacen. Pero esos puntos de asfixia son exactamente eso... puntos donde el tráfico se atragante. No hay nada de malo en impedir que los usuarios puedan navegar a Instagram o transmitir vídeos de gatos, pero no traten el tráfico de aplicaciones empresariales de misión crítica de la misma manera.
- Si DNS no está **contento,** no es nada bueno: la red mejor diseñada puede estar afectada por un DNS deficiente, ya sea mediante la reencuentrante de solicitudes a servidores de otras áreas del mundo o el uso de los servidores DNS de su ISP u otros servidores DNS públicos que almacenan en caché la información de resolución de DNS.
- **Solo porque así** era como lo solía hacer, no significa que eso sea lo que debería hacer ahora: la tecnología cambia constantemente y Office 365 no es una excepción. La aplicación de medidas de seguridad desarrolladas e implementadas para servicios locales o para controlar la navegación por la web no proporcionará el mismo nivel de seguridad y puede tener un impacto negativo significativo en el rendimiento.
- **Office 365 se creó para tener acceso** a través de Internet: eso es todo en pocas palabras. Independientemente de lo que quieras hacer entre los usuarios y el perímetro, el tráfico seguirá circulando por Internet una vez que salga de la red y antes de que llegue al nuestro. Incluso si usa Azure ExpressRoute para enrutar un poco de tráfico confidencial de latencia de la red directamente a la nuestra, la conectividad a Internet es absolutamente necesaria. Aceptarlo. No lo hagas demasiado.

## <a name="where-bad-choices-are-often-made"></a>Donde se suelen tomar decisiones malas

Aunque hay muchos lugares en los que se toman decisiones malas en nombre de la seguridad, estas son las que encuentro con más frecuencia con los clientes. Muchas conversaciones de clientes implican todo esto a la vez.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes en el perímetro

Muy pocos clientes están implementando entornos de campo verde y tienen años de experiencia con el modo en que trabajan sus usuarios y cómo es su salida de Internet. Tanto si los clientes tienen servidores proxy como si permiten el acceso directo y simplemente el tráfico saliente NAT, lo han estado haciendo durante años y no tienen en cuenta cuánto más van a empezar a mover a través de su perímetro a medida que tradicionalmente trasladan las aplicaciones internas a la nube.

El ancho de banda siempre es una preocupación, pero es posible que los dispositivos NAT no tengan suficiente potencia para controlar la carga aumentada y pueden empezar a cerrar prematuramente las conexiones para liberar recursos. La mayoría del software cliente que se conecta a Office 365 espera conexiones persistentes y un usuario que utiliza completamente Office 365 puede tener 32 o más conexiones simultáneas. Si el dispositivo NAT los está colocando prematuramente, es posible que esas aplicaciones no responsivas mientras intentan usar las conexiones que ya no están ahí. Cuando se dan por hecho y tratan de establecer nuevas conexiones, ponen aún más carga en el engranaje de red.

### <a name="localized-breakout"></a>Interrupción localizada

Todo lo demás de esta lista se debe a una cosa: salir de la red y llegar a la nuestra lo más rápido posible. El retroceso del tráfico de los usuarios a un punto de salida central, especialmente cuando ese punto de salida está en otra región de la que están los usuarios, introduce una latencia innecesaria y afecta tanto a la experiencia del cliente como a las velocidades de descarga. Microsoft tiene puntos de presencia en todo el mundo con front-ends para todos nuestros servicios y  emparejamiento establecidos con prácticamente todos los ISP principales, por lo que el enrutamiento del tráfico de los usuarios localmente garantiza que llegue a nuestra red rápidamente con una latencia mínima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>El tráfico de resolución DNS debe seguir la ruta de salida de Internet

Por supuesto, para que un cliente encuentre cualquier punto de conexión, debe usar DNS. Los servidores DNS de Microsoft evalúan el origen de las solicitudes DNS para garantizar que se devuelve la respuesta que, en términos de Internet, es más cercana al origen de la solicitud. Asegúrese de que el DNS está configurado para que las solicitudes de resolución de nombres vayan por la misma ruta que el tráfico de los usuarios, para no darles salida local, sino a un extremo de otra región. Esto significa permitir que los servidores DNS locales "vayan a raíz" en lugar de reenviar a servidores DNS en centros de datos remotos. Y tenga cuidado con los servicios DNS públicos y privados, que pueden almacenar en caché los resultados de una parte del mundo y atenderlas a solicitudes de otras partes del mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Para proxy o no para proxy, esa es la pregunta

Una de las primeras cosas que debe tener en cuenta es si se deben proxy las conexiones de los usuarios a Office 365. Ese es fácil; no haga proxy. Office 365 se accede a través de Internet, pero no es Internet. Es una extensión de los servicios principales y debe tratarse como tal. Cualquier cosa que desee que haga un proxy, como DLP o antimalware o inspección de contenido, ya está disponible en el servicio y se puede usar a escala y sin necesidad de descifrar las conexiones cifradas por TLS. Pero si realmente desea proxy tráfico que de otro modo no puede controlar, preste atención a nuestras instrucciones en y las [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) categorías de tráfico en [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) . Tenemos tres categorías de tráfico para Office 365. Optimizar y permitir realmente debe ir directo y omitir el proxy. El valor predeterminado se puede proxy. Los detalles están en esos documentos... léenlos.

La mayoría de los clientes que insisten en usar un proxy, cuando realmente ven lo que están haciendo, se dan cuenta de que cuando el cliente realiza una solicitud HTTP CONNECT al proxy, el proxy es ahora solo un enrutador adicional caro. Los protocolos en uso, como MAPI y RTC, ni siquiera son protocolos que los servidores proxy web entienden, por lo que incluso con la fisuración de TLS no se está obteniendo realmente ninguna seguridad adicional. Está *obteniendo* latencia adicional. Vea para obtener más información sobre esto, incluidas las categorías Optimizar, Permitir y Predeterminada [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) para Microsoft 365 tráfico.

Por último, considere el impacto general en el proxy y su respuesta correspondiente para hacer frente a ese impacto. A medida que se realizan más y más conexiones a través del proxy, puede disminuir el factor de escala TCP para que no tenga que almacenar en búfer tanto tráfico. He visto clientes donde sus servidores proxy estaban tan sobrecargados que usaban un factor de escala de 0. Dado que El factor de escala es un valor exponencial y nos gusta usar 8, cada reducción del valor del factor de escala es un gran impacto negativo en el rendimiento.

Tls Inspection significa SEGURIDAD. Pero en realidad no. Muchos clientes con servidores proxy quieren usarlos para inspeccionar todo el tráfico y eso significa que TLS "interrumpir e inspeccionar". Cuando lo hace para un sitio web al que se tiene acceso a través de HTTPS (no obstante los problemas de privacidad), es posible que el proxy tenga que hacerlo durante 10 o incluso 20 secuencias simultáneas durante unos cientos de milisegundos. Si hay una descarga grande o quizás un vídeo implicado, una o varias de esas conexiones pueden durar mucho más tiempo, pero en general, la mayoría de esas conexiones establecen, transfieren y cierran muy rápidamente. Al realizar la interrupción y la inspección, el proxy debe realizar el doble del trabajo. Para cada conexión del cliente al proxy, el proxy también debe realizar una conexión independiente al punto de conexión. Por lo tanto, 1 se convierte en 2, 2 se convierte en 4, 32 se convierte en 64... ¿ves a dónde voy? Probablemente haya dimensionado la solución de proxy correctamente para la navegación web típica, pero cuando intenta hacer lo mismo para las conexiones de cliente a Office 365, el número de conexiones simultáneas de larga duración puede ser de una magnitud mayor que la que ha dimensionado.

### <a name="streaming-isnt-important-except-that-it-is"></a>La transmisión por secuencias no es importante, excepto que *es*

Los únicos servicios de Office 365 que usan UDP Skype (pronto se retirarán) y Microsoft Teams. Teams UDP para el tráfico de streaming, incluido el uso compartido de audio, vídeo y presentación. El tráfico de streaming es en directo, como cuando tienes una reunión en línea con voz, vídeo y presentaciones de presentaciones o demostraciones. Estos usan UDP porque si los paquetes se descartan o llegan fuera de servicio, es prácticamente imperceptible para el usuario y la secuencia puede continuar.

Cuando no se permite el tráfico UDP saliente de los clientes al servicio, pueden volver a usar TCP. Pero si se descarta un paquete *TCP,* todo se detiene hasta que expire el tiempo de espera de retransmisión (RTO) y se pueda retransmitir el paquete que falta. Si un paquete llega sin orden, todo se detiene hasta que llegan los demás paquetes y se puede volver a ensamblar en orden. Ambos llevan a problemas perceptibles en el audio (¿recuerda Max Headroom?) y vídeo (hizo clic en algo... oh, ahí está) y conduce a un rendimiento deficiente y una mala experiencia del usuario. ¿Y recuerda lo que he expuesto anteriormente acerca de los servidores proxy? Cuando se fuerza un Teams cliente a usar un proxy, se fuerza a usar TCP. Por lo tanto, ahora estás causando impactos negativos en el rendimiento dos veces.

### <a name="split-tunneling-may-seem-scary"></a>El túnel dividido puede parecer espantoso

Pero no es así. Todas las conexiones Office 365 a través de TLS. We have been offering TLS 1.2 for quite a while now and will be disabling older versions soon because legacy clients still use them and that's a risk.

Forzar una conexión TLS, o 32 de ellas, para pasar por una VPN antes de ir al servicio no agrega seguridad. Agrega latencia y reduce el rendimiento general. En algunas soluciones VPN, incluso fuerza a UDP a túnel a través de TCP, lo que de nuevo tendrá un impacto muy negativo en el tráfico de streaming. Y, a menos que esté realizando la inspección tls, no hay ninguna desventaja, todo al revés. Un tema muy común entre los clientes, ahora que la mayoría de su personal es remoto, es que están viendo importantes impactos en el ancho de banda y el rendimiento al hacer que todos sus usuarios se conecten con una VPN, en lugar de configurar el túnel dividido para acceder a los puntos de conexión de categoría [Optimizar Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).

Es una solución fácil de hacer túnel dividido y es uno que debe hacer. Para obtener más información, asegúrese de revisar Optimizar Office 365 conectividad para usuarios remotos mediante túnel [dividido de VPN.](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="the-sins-of-the-past"></a>Los pecados del pasado

Muchas veces, la razón por la que se realizan malas decisiones proviene de una combinación de (1) no saber cómo funciona el servicio, (2) intentar cumplir con las directivas de la empresa que se escribieron antes de adoptar la nube y (3) equipos de seguridad que pueden no estar fácilmente convencidos de que hay más de una forma de lograr sus objetivos. Esperemos que lo anterior y los vínculos siguientes le ayudarán con el primero. Es posible que sea necesario el patrocinador ejecutivo para pasar del segundo. Abordar los objetivos de las directivas de seguridad, en lugar de sus métodos, ayuda con el tercero. Desde el acceso condicional a la moderación de contenido, DLP a la protección de la información, la validación de puntos de conexión y las amenazas de día cero: cualquier objetivo final que pueda tener una directiva de seguridad razonable puede lograrse con lo que está disponible en Office 365 y sin ninguna dependencia del engranaje de red local, los túneles VPN forzados y la interrupción e inspección de TLS.

En otras ocasiones, el hardware que se dimensionó y compró antes de que la organización empezara a mover a la nube simplemente no se puede escalar para controlar los nuevos patrones de tráfico y cargas. Si realmente debe enrutar todo el tráfico a través de un único punto de salida y/o proxy, esté preparado para actualizar el ancho de banda y el equipamiento de red según corresponda. Supervise cuidadosamente el uso en ambos, ya que la experiencia no disminuirá lentamente a medida que más usuarios se incorpore. Todo estará bien hasta que se llegue al punto de inflexión y, a continuación, todo el mundo sufra.

## <a name="exceptions-to-the-rules"></a>Excepciones a las reglas

Si su organización requiere restricciones de [inquilino,](/azure/active-directory/manage-apps/tenant-restrictions)deberá usar un proxy con interrupción TLS e inspeccionar para forzar el tráfico a través del proxy, pero no tiene que forzar todo el tráfico a través de él.  No es una propuesta de todo o nada, así que preste atención a lo que necesita modificar el proxy.

Si va a permitir la tunelización dividida pero también usar un proxy para el tráfico web general, asegúrese de que el archivo PAC define lo que debe ir directo, así como cómo definir tráfico interesante para lo que pasa a través del túnel VPN. Ofrecemos archivos PAC de ejemplo [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) para que esto sea más fácil de administrar.

## <a name="conclusion"></a>Conclusión

Decenas de miles de organizaciones, incluidas casi todas las de La Fortuna 500, usan Office 365 todos los días para sus funciones críticas de misión. Lo hacen de forma segura y lo hacen a través de Internet.

Independientemente de los objetivos de seguridad que tenga en juego, hay maneras de lograrlos que no requieren conexiones VPN, servidores proxy, interrupción e inspección de TLS, o salida centralizada de Internet para que el tráfico de los usuarios se despegue de la red y el nuestro lo antes posible, lo que proporciona el mejor rendimiento, independientemente de si la red es la sede de la empresa. , una oficina remota o ese usuario que trabaja en casa. Nuestra guía se basa en cómo se Office 365 los servicios de seguridad y para garantizar una experiencia de usuario segura y de rendimiento.

## <a name="further-reading"></a>Lectura adicional

[Principios Office 365 conectividad de red](../enterprise/microsoft-365-network-connectivity-principles.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Administrar puntos de conexión de Office 365](../enterprise/managing-office-365-endpoints.md)

[Dirección IP de Office 365 y servicio web de URL](../enterprise/microsoft-365-ip-web-service.md)

[Evaluar la red de Office 365](../enterprise/assessing-network-connectivity.md)

[Red de Office 365 y ajuste de rendimiento](../enterprise/network-planning-and-performance.md)

[Evaluar la conectividad de red de Office 365](../enterprise/assessing-network-connectivity.md)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](../enterprise/performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](../enterprise/performance-troubleshooting-plan.md)

[Redes de entrega de contenido](../enterprise/content-delivery-networks.md)

[Prueba de conectividad de Microsoft 365](https://connectivity.office.com/)

[Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de redes de Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 conectividad para usuarios remotos mediante túnel dividido de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md)