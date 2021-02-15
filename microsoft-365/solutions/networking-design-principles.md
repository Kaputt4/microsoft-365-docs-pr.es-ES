---
title: 'Conexión de red (a la nube): el punto de vista de un arquitecto'
description: Aprende a optimizar la red para la conectividad en la nube evitando los problemas más comunes.
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
ms.openlocfilehash: 175903949b639740ad00b29013d5748b99bdb2de
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771852"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Conexión de red (en la nube): el punto de vista de un arquitecto

En este artículo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), security & Compliance Architect en Microsoft, describe cómo optimizar la red para la conectividad en la nube evitando las dificultades más comunes. 

## <a name="about-the-author"></a>Acerca del autor

![Foto de Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Actualmente soy un especialista técnico principal en la región sudoriental que se centra en la seguridad y & cumplimiento. He trabajado con clientes que se han pasado a Office 365 durante los últimos 10 años. He trabajado con pequeñas tiendas con un número reducido de ubicaciones para agencias gubernamentales y empresas con millones de usuarios distribuidos por todo el mundo y muchos otros clientes en medio, con la mayoría con decenas de miles de usuarios, varias ubicaciones en varias partes del mundo, la necesidad de un mayor grado de seguridad y una gran variedad de requisitos de cumplimiento. He ayudado a cientos de empresas y millones de usuarios a pasar a la nube de forma segura y segura.

Con una experiencia en los últimos 25 años que incluye seguridad, infraestructura e ingeniería de red, y después de haber movido dos de mis empleados anteriores a Office 365 antes de unirse a Microsoft, he estado muchas veces en su lado de la tabla y recuerde cómo es. Aunque nunca dos clientes son iguales, la mayoría tienen necesidades similares y, al consumir un servicio estandarizado como cualquier plataforma SaaS o PaaS, los mejores enfoques tienden a ser los mismos.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>No es la red, sino cómo la usas (mal).

No importa cuántas veces sucede, nunca deja  de desamerme cómo los equipos de seguridad creativos y los equipos de redes intentan obtener información sobre cómo creen que deben conectarse a los servicios en la nube de Microsoft. Siempre hay alguna directiva de seguridad, estándar de cumplimiento o mejor manera de que se empeen en usar,  sin estar dispuestos a participar en una conversación sobre lo que están intentando lograr o cómo son mejores, más fáciles, más rentables y formas más eficaces de hacerlo.

Cuando este tipo de cosas se escalan a mí, normalmente estoy dispuesto a asumir el desafío y a llevarles a través de los cómo y los motivos y llevarlos a donde deben estar. Pero si estoy siendo completamente sincero, tengo que compartir que a veces quiero dejarles hacer lo que quieren y volver a decir que se lo he dicho cuando finalmente conceden que no funciona. Es posible que quiera hacerlo a veces, pero *no lo deseo.* Lo que hago es intentar explicar todo lo que voy a incluir en esta publicación. Independientemente de su rol, si su organización desea usar los servicios en la nube de Microsoft, es probable que haya alguna asidura en lo que sigue que puede ayudarle.

## <a name="guiding-principles"></a>Principios básicos

Empecemos con algunas reglas básicas en torno a lo que estamos haciendo aquí. Estamos analizando cómo conectarse de forma segura a los servicios en la nube para garantizar la complejidad mínima y el rendimiento máximo, a la vez que se mantiene la seguridad real. Nada de lo que sigue es contrario a nada de eso, incluso si usted, o su cliente, no podrá usar su servidor proxy favorito para todo.

- **El hecho de que pueda,** no significa que deba : O parafraseando al Dr. IanGli de la película Desfilacionado "... Sí, sí, pero el equipo de seguridad estaba tan ocupado con saber si podían o no no detenerse a pensar si deberían".
- **La seguridad no significa complejidad:** no es más seguro solo porque se invierte más dinero, se enruta a través de más dispositivos o se hacen clic en más botones.
- Se tiene acceso a **Office 365** a través de Internet: pero eso no es lo mismo que Office 365 es Internet. Es un servicio SaaS administrado por Microsoft y administrado por usted. A diferencia de los sitios web que visita en Internet, en realidad puede echar un vistazo detrás del proceso y aplicar los controles que necesita para cumplir las directivas y los estándares de cumplimiento, siempre y cuando comprenda que, aunque puede cumplir sus objetivos, es posible que solo tenga que hacerlo de una manera diferente.
- Los puntos de cola son feos, las interrupciones **localizadas** son buenas: todos siempre quieren volver a descargar todo su tráfico de Internet para todos sus usuarios a algún punto central, normalmente para que puedan supervisarla y aplicar la directiva, pero a menudo porque es más económica que aprovisionar acceso a Internet en todas sus ubicaciones, o es simplemente cómo lo hacen. Pero esos puntos de astilla son exactamente eso... puntos donde se atragante el tráfico. No hay nada de malo en impedir que los usuarios puedan navegar a Twitter o a vídeos de gatos en streaming, pero no trates tu tráfico de aplicaciones empresariales fundamentales de la misma manera.
- Si EL DNS no está **satisfecho,** no está nada contento: la red mejor diseñada puede estar afectada por un DNS deficiente, ya sea mediante solicitudes recurrentes a servidores de otras áreas del mundo o mediante los servidores DNS del ISP u otros servidores DNS públicos que almacena en caché la información de resolución DNS.
- **Just because that's how you used to do it, doesn't mean that's how you should do it now**: Technology changes constantly and Office 365 is no exception. La aplicación de medidas de seguridad desarrolladas e implementadas para los servicios locales o para controlar las incidencias web no proporcionará el mismo nivel de garantía de seguridad y puede tener un impacto negativo significativo en el rendimiento.
- **Office 365 se creó** para tener acceso a través de Internet: eso es todo en pocas palabras. Independientemente de lo que quieras hacer entre los usuarios y el perímetro, el tráfico sigue circulando por Internet una vez que sale de la red y antes de que llegue al nuestro. Incluso si usa Azure ExpressRoute para enrutar parte del tráfico confidencial de latencia de su red directamente a la nuestra, la conectividad a Internet es absolutamente necesaria. Aceptarlo. No lo hagas demasiado.

## <a name="where-bad-choices-are-often-made"></a>Donde se suelen tomar decisiones no correctas

Aunque hay muchos lugares en los que se toman decisiones mal en nombre de la seguridad, estos son los que encuentro con más frecuencia con los clientes. Muchas conversaciones de clientes implican todas ellas a la vez.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes en el borde

Muy pocos clientes están implementando entornos de campo verde y tienen años de experiencia con el modo en que sus usuarios trabajan y cómo es su salida de Internet. Tanto si los clientes tienen servidores proxy como si permiten el acceso directo y, simplemente, el tráfico saliente nat, lo han hecho durante años y no tienen en cuenta cuánto más van a empezar a desplazarse a través de su perímetro a medida que tradicionalmente trasladan aplicaciones internas a la nube.

El ancho de banda siempre es un problema, pero es posible que los dispositivos NAT no tengan suficiente potencia para controlar el aumento de la carga y puedan iniciar de forma prematura el cierre de conexiones para liberar recursos. La mayoría del software cliente que se conecta a Office 365 espera conexiones persistentes y un usuario que utiliza completamente Office 365 puede tener 32 o más conexiones simultáneas. Si el dispositivo NAT los deja antes de tiempo, es posible que esas aplicaciones no responsiven al intentar usar las conexiones que ya no están ahí. Cuando se dan por hecho e intentan establecer nuevas conexiones, ponen aún más carga en el engranaje de red.

### <a name="localized-breakout"></a>Interrupción localizada

Todo lo demás de esta lista se trata de una cosa: salir de la red y entrar en la nuestra lo más rápido posible. Al volver a poner el tráfico de los usuarios en un punto de salida central, especialmente cuando ese punto de salida está en otra región de la que están los usuarios, se introduce una latencia innecesaria y afecta tanto a la experiencia del cliente como a las velocidades de descarga. Microsoft tiene puntos de presencia en todo el mundo con front-ends para todos nuestros servicios y emparejamiento establecido con prácticamente todos los ISP principales, por lo que enrutar el tráfico de los usuarios *localmente* garantiza que llegue a nuestra red rápidamente con una latencia mínima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>El tráfico de resolución DNS debe seguir la ruta de salida de Internet

Por supuesto, para que un cliente encuentre cualquier punto de conexión, debe usar DNS. Los servidores DNS de Microsoft evalúan el origen de las solicitudes DNS para garantizar que se devuelve la respuesta más cercana, en términos de Internet, al origen de la solicitud. Asegúrese de que su DNS está configurado para que las solicitudes de resolución de nombres vayan en la misma ruta que el tráfico de los usuarios, no le dé salida local, sino a un punto de conexión de otra región. Esto significa permitir que los servidores DNS locales "vayan a raíz" en lugar de reenviar a servidores DNS en centros de datos remotos. Y tenga cuidado con los servicios DNS públicos y privados, que pueden almacenar en caché los resultados de una parte del mundo y atenderlas a las solicitudes de otras partes del mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Para proxy o no para proxy, esa es la pregunta

Una de las primeras cosas que se debe tener en cuenta es si se van a usar conexiones de usuarios proxy a Office 365. Ese es fácil; no realice proxy. Se tiene acceso a Office 365 a través de Internet, pero no a Internet. Es una extensión de los servicios principales y debe tratarse como tal. Cualquier cosa que desee que haga un proxy, como DLP, antimalware o inspección de contenido, ya está disponible en el servicio y se puede usar a escala y sin necesidad de descifrar conexiones cifradas con TLS. Pero si realmente quieres usar proxy de tráfico que de otro modo no puedes controlar, presta atención a nuestras instrucciones y a [https://aka.ms/pnc](https://aka.ms/pnc) las categorías de tráfico en [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Tenemos tres categorías de tráfico para Office 365. Optimizar y permitir realmente debe ir directo y omitir el proxy. El valor predeterminado se puede convertir en proxy. Los detalles están en esos documentos... léalos.

La mayoría de los clientes que se empleó en usar un proxy, cuando realmente miran lo que están haciendo, se dan cuenta de que cuando el cliente realiza una solicitud HTTP CONNECT al proxy, el proxy es ahora solo un enrutador adicional costoso. Los protocolos en uso, como MAPI y RTC, ni siquiera son protocolos que los servidores proxy web entienden, por lo que incluso con la fisuración de TLS no se está obteniendo realmente ninguna seguridad adicional. Está *obteniendo* latencia adicional. Para obtener más información, vea las categorías Optimizar, Permitir y Predeterminada para el tráfico de [https://aka.ms/pnc](https://aka.ms/pnc) Microsoft 365.

Por último, tenga en cuenta el impacto general en el proxy y su respuesta correspondiente para hacer frente a ese impacto. A medida que se realizan más conexiones a través del proxy, puede disminuir el factor de escala TCP para que no tenga que almacenar en búfer tanto tráfico. He visto a los clientes donde sus servidores proxy estaban tan sobrecargados que usaban un factor de escala de 0. Dado que el factor de escala es un valor exponencial y nos gusta usar 8, cada reducción del valor del factor de escala es un gran impacto negativo en el rendimiento.

TLS Inspection means SECURITY! Pero no realmente. Muchos clientes con servidores proxy quieren usarlos para inspeccionar todo el tráfico, lo que significa que TLS "interrumpirá e inspeccionará". Cuando lo hace para un sitio web al que se accede a través de HTTPS (dudas sobre la privacidad), es posible que el proxy tenga que hacerlo durante 10 o incluso 20 secuencias simultáneas durante unos cientos de milisegundos. Si hay una descarga grande o quizás un vídeo implicado, una o varias de esas conexiones pueden durar mucho más tiempo, pero en su totalidad, la mayoría de esas conexiones se establecen, transfieren y se cierran muy rápidamente. Al realizar la interrupción y la inspección, el proxy debe realizar el doble del trabajo. Para cada conexión desde el cliente al proxy, el proxy también debe realizar una conexión independiente al punto de conexión. Por lo tanto, 1 se convierte en 2, 2 se convierte en 4, 32 se convierte en 64... ¿ve hacia dónde voy? Probablemente haya dimensionado la solución de proxy correctamente para el tráfico web típico, pero cuando intenta hacer lo mismo para las conexiones de cliente a Office 365, el número de conexiones simultáneas de larga duración puede ser un orden de magnitud mayor que el tamaño para el que se ha dimensionado.

### <a name="streaming-isnt-important-except-that-it-is"></a>La transmisión por secuencias no es importante, excepto que *es*

Los únicos servicios de Office 365 que usan UDP son Skype (que pronto se retirará) y Microsoft Teams. Teams usa UDP para el tráfico de streaming, incluido el uso compartido de audio, vídeo y presentación. El tráfico de streaming es en directo, como cuando tienes una reunión en línea con voz, vídeo y presentación de presentaciones o demostraciones. Estos usan UDP porque si los paquetes se descartan o llegan fuera de su orden, el usuario prácticamente no nota y la secuencia puede seguir adelante.

Si no permite el tráfico UDP saliente de los clientes al servicio, pueden volver a usar TCP. Pero si se descarta un paquete *TCP,* todo se detiene hasta que expira el tiempo de espera de retransmisión (RTO) y se puede retransmitir el paquete que falta. Si un paquete llega fuera de servicio, todo se detiene hasta que llegan los demás paquetes y se pueden volver a ensamblar en orden. Ambos llevan a problemas perceptibles en el audio (¿recuerda Max Headroom?) y vídeo (¿has hecho clic en algo... oh, ahí está) y conduce a un rendimiento deficiente y una experiencia de usuario deficiente. ¿Y recuerda lo que mencioné anteriormente sobre los servidores proxy? Cuando se fuerza a un cliente de Teams a usar un proxy, se fuerza para que use TCP. Por lo tanto, ahora estás causando impactos negativos en el rendimiento dos veces.

### <a name="split-tunneling-may-seem-scary"></a>El túnel dividido puede parecer terrible

Pero no lo es. Todas las conexiones a Office 365 se encuentran a través de TLS. We have been offering TLS 1.2 for quite a while now and will be disabling older versions soon because legacy clients still use them and that's a risk.

Forzar una conexión TLS, o 32 de ellas, para pasar por una VPN antes de ir al servicio no agrega seguridad. Agrega latencia y reduce el rendimiento general. En algunas soluciones vpn, incluso obliga a UDP a túnel a través de TCP, lo que de nuevo tendrá un impacto muy negativo en el tráfico de streaming. Y, a menos que esté realizando la inspección de TLS, no hay ninguna desventaja. Un tema muy común entre los clientes, ahora que la mayoría de sus empleados es remoto, es que están viendo un gran impacto en el ancho de banda y el rendimiento al hacer que todos sus usuarios se conecten mediante una VPN, en lugar de configurar el túnel dividido para obtener acceso a los puntos de conexión de [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories)de la categoría Optimizar.

Es una solución fácil de hacer el túnel dividido y es uno de los que debe hacer. Para obtener más información, asegúrese de revisar Optimizar la conectividad de [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)para usuarios remotos que usan túnel dividido de VPN.

## <a name="the-sins-of-the-past"></a>Los senos del pasado

Muchas veces, la razón por la que se realizan decisiones no correctas proviene de una combinación de (1) no saber cómo funciona el servicio, (2) intentar cumplir con las directivas de la empresa que se escribieron antes de adoptar la nube y (3) equipos de seguridad que pueden no estar fácilmente convencidas de que hay más de una forma de lograr sus objetivos. Esperamos que lo anterior y los vínculos siguientes le ayuden con el primero. Es posible que se requiera el apoyo del ejecutivo para pasar por el segundo. Abordar los objetivos de las directivas de seguridad, en lugar de sus métodos, ayuda con el tercero. Desde el acceso condicional a la moderación de contenido, DLP a la protección de la información, la validación de puntos de conexión a las amenazas de día cero: cualquier objetivo final que pueda tener una directiva de seguridad razonable se puede lograr con lo que está disponible en Office 365, y sin ninguna dependencia en el engranaje de red local, túneles VPN forzados e interrupción e inspección tls.

Otras veces, el hardware que se ha dimensionado y comprado antes de que la organización empezara a moverse a la nube simplemente no se puede escalar para controlar las nuevas cargas y patrones de tráfico. Si realmente debe enrutar todo el tráfico a través de un único punto de salida o proxy, esté preparado para actualizar el ancho de banda y el equipo de red en consecuencia. Supervise cuidadosamente el uso en ambos, ya que la experiencia no disminuirá lentamente a medida que se incorpore más usuarios. Todo estará bien hasta que se alcance el punto de resalte y, a continuación, todo el mundo sufra.

## <a name="exceptions-to-the-rules"></a>Excepciones a las reglas

Si su organización requiere [restricciones](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)de espacio empresarial, tendrá que usar un proxy con interrupción TLS e inspeccionar para forzar el tráfico a través del proxy, pero no tiene que forzar todo el tráfico a través de él.  No es una propuesta de todo o nada, así que preste atención a lo que necesita modificar el proxy.

Si va a permitir el túnel dividido, pero también va a usar un proxy para el tráfico web general, asegúrese de que el archivo PAC define lo que debe ir directamente, así como cómo definir tráfico interesante para lo que pasa a través del túnel VPN. Ofrecemos archivos PAC de ejemplo para que [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) esto sea más fácil de administrar.

## <a name="conclusion"></a>Conclusión

Decenas de miles de organizaciones, incluidos casi todos los Miembros de la Familia 500, usan Office 365 todos los días para sus funciones críticas. Lo hacen de forma segura y lo hacen a través de Internet.

Independientemente de los objetivos de seguridad que tenga en juego, hay formas de lograrlos que no requieren conexiones VPN, servidores proxy, interrupción e inspección tls, o salida centralizada de Internet para sacar el tráfico de los usuarios de la red y del nuestro tan rápido como sea posible, lo que proporciona el mejor rendimiento, independientemente de si la red es la sede de la empresa, una oficina remota o ese usuario que trabaja en casa. Nuestra guía se basa en la forma en que se construyen los servicios de Office 365 y para garantizar una experiencia de usuario segura y de rendimiento.

## <a name="further-reading"></a>Lectura adicional

[Principios de conectividad de red de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Direcciones URL e intervalos de direcciones IP de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Administrar puntos de conexión de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)

[Dirección IP de Office 365 y servicio web de URL](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-ip-web-service)

[Evaluar la red de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Red de Office 365 y ajuste de rendimiento](https://docs.microsoft.com/microsoft-365/enterprise/network-planning-and-performance)

[Evaluar la conectividad de red de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](https://docs.microsoft.com/microsoft-365/enterprise/performance-tuning-using-baselines-and-history)

[Plan de solución de problemas de rendimiento para Office 365](https://docs.microsoft.com/microsoft-365/enterprise/performance-troubleshooting-plan)

[Redes de entrega de contenido](https://docs.microsoft.com/microsoft-365/enterprise/content-delivery-networks)

[Prueba de conectividad de Microsoft 365](https://connectivity.office.com/)

[Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de redes de Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Conectividad de Office 365 para usuarios remotos que usan túnel dividido de VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


