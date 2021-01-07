---
title: 'Redes hacia arriba (en la nube): el punto de vista de un arquitecto'
description: Obtenga información sobre cómo optimizar la red para la conectividad en la nube evitando los errores más comunes.
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
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Redes hacia arriba (en la nube): el punto de vista de un arquitecto

En este artículo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & el arquitecto de cumplimiento de Microsoft, se describe cómo optimizar la red para la conectividad en la nube al evitar los errores más comunes. 

## <a name="about-the-author"></a>Acerca del autor

![Ed foto de Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Actualmente soy especialista técnico principal en la región del sudeste que se centra en el cumplimiento de & de seguridad. He trabajado con clientes que se han migrado a Office 365 durante los últimos 10 años. He trabajado con tiendas más pequeñas con unas pocas ubicaciones para agencias gubernamentales y empresas con millones de usuarios distribuidos en todo el mundo y muchos otros clientes en el pasado, con la mayoría de miles de usuarios, varias ubicaciones en distintas partes del mundo, la necesidad de un mayor nivel de seguridad y una gran variedad de requisitos de cumplimiento. He ayudado a cientos de empresas y millones de usuarios a pasarse a la nube de manera segura.

Con un fondo de los últimos 25 años que incluye la seguridad, la infraestructura y la ingeniería de red, y que han movido dos de mis empresarios anteriores a Office 365 antes de unirse a Microsoft, he estado en el lado de la tabla durante mucho tiempo y recuerde lo que es como. Aunque no todos los clientes son iguales, la mayoría tienen necesidades similares y, al consumir un servicio estandarizado, como una plataforma SaaS o PaaS, los mejores métodos tienden a ser los mismos.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>No es la red: la forma en que está (mis) usando.

Independientemente del número de veces que se produzca, nunca puede sorprender cómo los equipos de seguridad *creativa* y los equipos de redes intentan obtener acceso a los servicios en la nube de Microsoft. Siempre hay una directiva de seguridad, un estándar de cumplimiento o una mejor manera de que insistir en el uso de, sin estar dispuesto a participar en una conversación sobre lo que está intentando realizar, ni en *Cómo* son mejores, más sencillas, rentables y formas más eficaces de hacerlo.

Cuando se les asigna este tipo de cosas, normalmente estoy dispuesto a hacer el reto y remitirnos a través de la forma y el porqué y obtenerlas en el lugar donde deben estar. Pero si me estoy haciendo por completo Frank, tengo que compartir que a veces quiero dejarles que hagan lo que van, y volvamos a decir que me dijo que cuando finalmente concedía que no funciona. Es posible que le interese hacerlo a veces, pero *no*. Lo que voy a intentar es explicar todo lo que voy a incluir en esta publicación. Independientemente de cuál sea su rol, si su organización desea usar los servicios en la nube de Microsoft, es probable que tenga algo de información sobre lo que puede resultar útil.

## <a name="guiding-principles"></a>Principios de guía

Comencemos con algunas reglas básicas alrededor de lo que estamos haciendo aquí. Estamos hablando de cómo conectarse de forma segura a los servicios en la nube para garantizar la complejidad mínima y el rendimiento máximo, a la vez que se mantiene la seguridad real. Ninguna de las siguientes características es un contador de esto, incluso si usted o su cliente no van a usar su servidor proxy preferido para todo.

- El **hecho de que no signifique que deba**: o para Paraphrase Dr. Ian Malcolm de la película de Jurassic Park "... sí, pero el equipo de seguridad está preocupado con independencia de si es posible que no se hayan detenido para pensar si deberían.
- **La seguridad no significa complejidad**: no es más seguro solo porque gasta más dinero, enruta a través de más dispositivos o hace clic en más botones.
- **Se obtiene acceso a office 365 a través de Internet**: pero no es lo mismo que Office 365 es Internet. Es un servicio SaaS administrado por Microsoft y administrado por usted. A diferencia de los sitios web que visita en Internet, tiene la posibilidad de buscar detrás de la cortina y puede aplicar los controles que necesita para cumplir las directivas y los estándares de cumplimiento, siempre que comprenda que, aunque pueda cumplir con los objetivos, es posible que tenga que hacerlo de una manera distinta.
- **Chokepoints son malas, las sesiones individuales localizadas son buenas**: todos los usuarios siempre quieren backhaul todo el tráfico de Internet para todos sus usuarios a algún punto central, normalmente para que puedan supervisarlo y aplicar la Directiva, pero con frecuencia porque es más barato que aprovisionar el acceso a Internet en todas sus ubicaciones, o es solo cómo hacerlo. Pero esos chokepoints son exactamente eso... puntos en los que se retraerá el tráfico. No hay ningún problema para evitar que los usuarios puedan navegar a Instagram o transmitir vídeos por secuencias de vídeo, pero no trate el tráfico de la aplicación empresarial de misión crítica del mismo modo.
- **Si el DNS no está contento, no se alegra nada**: la mejor red diseñada puede ser hamstrung por un DNS pobre, ya sea al Reenviar solicitudes a servidores de otras áreas del mundo o a través de los servidores DNS de su ISP u otros servidores DNS públicos que almacenen en caché la información de resolución DNS.
- **El hecho de que así sea cómo lo usó, no significa cómo debe hacerlo ahora**: los cambios tecnológicos constantemente y Office 365 no es una excepción. La aplicación de medidas de seguridad desarrolladas e implementadas para los servicios locales o para controlar la navegación por la web no proporcionará el mismo nivel de garantía de seguridad y puede tener un impacto negativo significativo en el rendimiento.
- **Office 365 se ha creado para que se pueda obtener acceso a él a través de Internet**: eso es un resumen. Independientemente de lo que quiera hacer entre los usuarios y el perímetro, el tráfico continúa a través de Internet una vez que sale de la red y antes de que se ponga en nuestro. Incluso si usa Azure ExpressRoute para enrutar el tráfico sensible a la latencia de la red directamente al nuestro, es absolutamente necesario tener conectividad a Internet. Aceptarla. No lo pensamos.

## <a name="where-bad-choices-are-often-made"></a>Cuándo se suelen realizar opciones erróneas

Aunque hay muchos lugares en los que se toman malas decisiones en el nombre de la seguridad, estos son los que encuentro con más frecuencia con los clientes. Muchas conversaciones de los clientes involucran todas a la vez.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes en el servidor perimetral

Muy pocos clientes están implementando entornos de Greenfield y tienen años de experiencia con el funcionamiento de sus usuarios y su salida a Internet es similar a la de. Si los clientes tienen servidores proxy o permiten el acceso directo y simplemente el tráfico saliente NAT, han estado llevando a cabo durante años y no tienen en cuenta cuánto más van a empezar a pasar a través de su perímetro a medida que se mueven las aplicaciones internas tradicionalmente a la nube.

El ancho de banda siempre es un problema, pero es posible que los dispositivos NAT no tengan la capacidad suficiente para controlar el aumento de la carga y pueden iniciar anticipadamente las conexiones para liberar recursos. La mayor parte del software de cliente que se conecta a Office 365 espera que las conexiones persistentes, y un usuario que usa completamente Office 365 puede tener 32 o más conexiones simultáneas. Si el dispositivo NAT Los elimina antes de tiempo, esas aplicaciones podrían dejar de responder al intentar usar las conexiones que ya no están. Cuando reciben e intentan establecer nuevas conexiones, ofrecen incluso más carga en el engranaje de la red.

### <a name="localized-breakout"></a>Desglose localizado

Todo lo que se muestra en esta lista se refiere a un elemento: sacar de la red y hacerlo tan rápido como sea posible. La reversión del tráfico de los usuarios a un punto de salida central, sobre todo cuando ese punto de salida está en otra región que los usuarios, presenta una latencia innecesaria y afecta tanto a la experiencia del cliente como a la velocidad de descarga. Microsoft tiene puntos de presencia en todo el mundo con servidores front-end para todos nuestros servicios y emparejamiento establecidos con prácticamente todos los principales ISP, por lo que el enrutamiento del tráfico de los usuarios de *forma local* garantiza que entra en la red rápidamente con una latencia mínima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>El tráfico de resolución DNS debe seguir la ruta de salida de Internet

Por supuesto, para que un cliente encuentre cualquier punto de conexión, debe usar DNS. Los servidores DNS de Microsoft evalúan el origen de las solicitudes de DNS para asegurarse de que se devuelve la respuesta que es, en términos de Internet, más cercana al origen de la solicitud. Asegúrese de que su DNS está configurado para que las solicitudes de resolución de nombres salgan de la misma ruta que el tráfico de los usuarios, Lest que les dé salida local, pero a un extremo en otra región. Esto significa permitir a los servidores DNS locales "ir a la raíz" en lugar de reenviar a los servidores DNS en centros de datos remotos. Y vea los servicios DNS públicos y privados, que pueden almacenar en la memoria caché los resultados de una parte del mundo y atenderlos a las solicitudes de otras partes del mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>En proxy o no en proxy, es la pregunta

Una de las primeras cosas que hay que tener en cuenta es si se van a canalizar las conexiones de los usuarios a Office 365. Es fácil; no proxy. Se tiene acceso a Office 365 a través de Internet, pero no es Internet. Es una extensión de sus servicios principales y debe tratarse como tal. Es posible que desee hacer un proxy, como DLP o antimalware o la inspección de contenido, que ya está disponible en el servicio, y que puede usarse a escala y sin necesidad de descifrar conexiones cifradas con TLS. Pero si realmente desea el tráfico de proxy que no puede controlar, preste atención a nuestras instrucciones en [https://aka.ms/pnc](https://aka.ms/pnc) y a las categorías de tráfico en [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Tenemos tres categorías de tráfico para Office 365. Optimizar y permitir realmente debería ir directamente y omitir el proxy. El valor predeterminado puede ser proxy. Los detalles están en esos documentos... leerlos.

La mayoría de los clientes que insisten en usar un proxy, cuando realmente ven lo que hacen, se dan cuenta de que cuando el cliente realiza una solicitud HTTP CONNECT al proxy, el proxy ahora es simplemente un costoso enrutador adicional. Los protocolos en uso, como MAPI y RTC, no son pares que los proxies web comprenden, por lo que, incluso con el descifrado de TLS, no se obtiene una seguridad adicional. *Está* recibiendo latencia adicional. Consulte [https://aka.ms/pnc](https://aka.ms/pnc) para obtener más información sobre esto, incluidas las categorías optimizar, permitir y predeterminado para el tráfico de Microsoft 365.

Por último, tenga en cuenta el impacto general en el proxy y su respuesta correspondiente para tratar con ese impacto. A medida que se van realizando más conexiones a través del proxy, puede disminuir el factor de escala TCP para que no tenga que almacenar en búfer el tráfico. He visto clientes en los que sus servidores proxy estaban tan sobrecargados que estaban usando un factor de escala de 0. Dado que el factor de escala es un valor exponencial y nos gusta usar 8, cada reducción en el valor del factor de escala es un gran impacto negativo en el rendimiento.

La inspección de TLS significa seguridad. Pero, en realidad, no. Muchos clientes con servidores proxy quieren utilizarlos para inspeccionar todo el tráfico y esto significa "romper e inspeccionar" TLS. Cuando lo hace para un sitio web al que se tiene acceso a través de HTTPS (independientemente de las preocupaciones de privacidad), es posible que el proxy tenga que hacerlo para 10 o incluso 20 flujos simultáneos para unos pocos cientos de milisegundos. Si hay una descarga grande o quizá un vídeo implicado, una o varias de esas conexiones pueden durar mucho más tiempo, pero, en su totalidad, la mayoría de esas conexiones establecen, transfieren y se cierran rápidamente. Interrumpir e inspeccionar significa que el proxy debe duplicar el trabajo. Para cada conexión del cliente al proxy, el proxy también debe volver a establecer una conexión independiente al extremo. Por lo tanto, 1 se convierte en 2, 2 se convierte en 4, 32 se convierte en 64... vea dónde voy? Probablemente, el tamaño de la solución proxy sea adecuado para la navegación web típica, pero cuando intente hacer lo mismo para las conexiones de cliente a Office 365, el número de conexiones simultáneas y de larga duración puede ser un orden de magnitud mayor que el que ha ajustado.

### <a name="streaming-isnt-important-except-that-it-is"></a>La transmisión por secuencias no es importante, excepto que *es*

Los únicos servicios en Office 365 que usan UDP son Skype (que pronto se retirarán) y Microsoft Teams. Microsoft Teams usa UDP para el tráfico de transmisión que incluye audio, vídeo y uso compartido de presentaciones. El tráfico de transmisión por secuencias está activo, como cuando tiene una reunión en línea con las Barajas de voz, vídeo y presentación o realizando demostraciones. Usan UDP porque, si se eliminan paquetes o llegan fuera de orden, es prácticamente inadvertible por el usuario y la transmisión puede seguir adelante.

Cuando no permite el tráfico UDP saliente de los clientes al servicio, puede recurrir a usar TCP. Pero si se interrumpe un paquete TCP, *todo se detiene* hasta que expira el tiempo de espera de retransmisión (RTO) y el paquete que falta puede retransmitirse. Si un paquete llega fuera del orden, todo se detiene hasta que los otros paquetes llegan y se pueden volver a ensamblar en orden. Ambos conducen a problemas perceptibles del audio (Recuerde el máximo espacio?) y vídeo (hizo clic en algo... Ah, ahí es) y conduce a un rendimiento deficiente y una experiencia de usuario deficiente. ¿Recuerda qué he colocado sobre los servidores proxy? Cuando se fuerza a un cliente de Teams a usar un proxy, se fuerza a que use TCP. Ahora está causando un impacto negativo en el rendimiento dos veces.

### <a name="split-tunneling-may-seem-scary"></a>La tunelización dividida puede parecer temida

Pero no lo es. Todas las conexiones a Office 365 están a través de TLS. Hemos estado ofreciendo TLS 1,2 por bastante tiempo y se deshabilitarán las versiones anteriores pronto como los clientes heredados aún los utilizan y ese es un riesgo.

Forzar una conexión TLS, o 32 de ellas, para desplazarse a través de una VPN antes de que pasen al servicio no agrega seguridad. Se agrega latencia y se reduce el rendimiento general. En algunas soluciones de VPN, incluso fuerza a UDP a atravesar TCP, lo que de nuevo tendrá un impacto muy negativo en el tráfico de transmisión por secuencias. Y, a menos que realice una inspección de TLS, no hay ninguna desventaja. Un tema muy común entre los clientes, ahora que la mayor parte de sus empleados es remoto, es que ven impactos significativos en el ancho de banda y el rendimiento para que todos sus usuarios se conecten mediante una VPN, en lugar de configurar la tunelización dividida para obtener acceso a [optimizar los puntos de conexión de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).

Es una solución sencilla para realizar un túnel dividido y es uno de los que debe hacer. Para obtener más información, consulte [optimizar la conectividad de Office 365 para usuarios remotos mediante la tunelización dividida de VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel).

## <a name="the-sins-of-the-past"></a>El pecados del pasado

Muchas veces, el motivo por el que se han tomado decisiones incorrectas proviene de una combinación de (1) que no sabe cómo funciona el servicio, (2) intenta adherirse a las directivas de la empresa que se escribieron antes de adoptar la nube, y (3) los equipos de seguridad que podrían no estar fácilmente convencidos de que hay más de una forma de lograr sus objetivos Espero que el anterior y los siguientes vínculos le ayudarán con el primero. Puede que sea necesario un patrocinio ejecutivo para llegar más allá del segundo. La tercera es la solución a los objetivos de las directivas de seguridad, en lugar de a los métodos. Desde el acceso condicional a la moderación del contenido, la DLP, la protección de la información, la validación de extremos a amenazas de día cero: cualquier objetivo final puede tener una directiva de seguridad razonable con lo que está disponible en Office 365 y sin ninguna dependencia en el engranaje de red local, los túneles VPN forzados y la interrupción TLS y la inspección.

Otras horas, el hardware que se ha dimensionado y comprado antes de que la organización comience a pasar a la nube no se puede escalar verticalmente para controlar los nuevos patrones de tráfico y cargas. Si realmente debe enrutar todo el tráfico a través de un único punto de salida y/o proxy, esté preparado para actualizar el equipo de red y el ancho de banda según corresponda. Supervise minuciosamente la utilización de ambos, ya que la experiencia no disminuirá lentamente a medida que más usuarios estén incorporados. Todo será correcto hasta que se alcance el punto de superposición y, a continuación, todos los usuarios se vean afectados.

## <a name="exceptions-to-the-rules"></a>Excepciones a las reglas

Si su organización requiere [restricciones de espacio empresarial](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions), deberá usar un proxy con la interrupción TLS e inspeccionar para forzar el tráfico a través del proxy, pero no tiene que forzar todo el tráfico que lo atraviese.  No es una propuesta de nada o nada, así que preste atención a lo que el proxy debe modificar.

Si va a permitir la tunelización dividida, pero también usa un proxy para el tráfico web general, asegúrese de que el archivo PAC define lo que debe ir directamente y de cómo se define el tráfico interesante para el que pasa por el túnel VPN. Ofrecemos archivos PAC de ejemplo en [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) para que resulte más fácil de administrar.

## <a name="conclusion"></a>Conclusión

Decenas de miles de organizaciones, incluida casi todas las Fortune 500, usan Office 365 diariamente para sus funciones de misión crítica. Lo hacen de manera segura y lo hacen a través de Internet.

Independientemente de los objetivos de seguridad que tenga en juego, hay formas de llevarlos a cabo que no requieren conexiones VPN, servidores proxy, la interrupción e inspección de TLS o la salida de Internet centralizada para que el tráfico de los usuarios esté fuera de la red y en el nuestro equipo tan rápido como sea posible, lo que proporciona el mejor rendimiento, independientemente de si la red es la oficina o que el usuario trabaja en casa. Nuestra guía se basa en cómo se crean los servicios 365 de Office y para garantizar una experiencia de usuario segura y de rendimiento.

## <a name="further-reading"></a>Lecturas adicionales

[Los principios de conectividad de red de Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

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

[Office 365 conectividad para usuarios remotos mediante la tunelización dividida de VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


