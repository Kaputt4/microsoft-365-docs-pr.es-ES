---
title: Enrutamiento con ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: En este artículo, obtenga información sobre los requisitos de enrutamiento, los circuitos y los dominios de enrutamiento de Azure ExpressRoute para su uso con Office 365.
ms.openlocfilehash: 4596f3fb05b39b8044c645db3bfcb1bd5fbe8c18
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67660825"
---
# <a name="routing-with-expressroute-for-office-365"></a>Enrutamiento con ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para comprender correctamente el enrutamiento del tráfico a Office 365 mediante Azure ExpressRoute, necesitará una comprensión firme de los requisitos básicos de [enrutamiento de ExpressRoute](/azure/expressroute/expressroute-routing) y los [circuitos y dominios de enrutamiento de ExpressRoute](/azure/expressroute/expressroute-circuit-peerings). Estos establecen los aspectos básicos para usar ExpressRoute en los que se basarán Office 365 clientes.
  
Algunos de los elementos clave de los artículos anteriores que necesitará comprender incluyen:
  
- Los circuitos ExpressRoute no están asignados a una infraestructura física específica, pero son una conexión lógica realizada en una única ubicación de emparejamiento por Microsoft y un proveedor de emparejamiento en su nombre.

- Hay una asignación 1:1 entre un circuito ExpressRoute y una clave de cliente.

- Cada circuito puede admitir dos relaciones de emparejamiento independientes (emparejamiento privado de Azure y emparejamiento de Microsoft); Office 365 requiere emparejamiento de Microsoft.

- Cada circuito tiene un ancho de banda fijo que se comparte entre todas las relaciones de emparejamiento.

- Las direcciones IPv4 públicas y los números de AS públicos que se usarán para el circuito ExpressRoute deben validarse como propiedad de usted o asignarse exclusivamente por el propietario del intervalo de direcciones.

- Los circuitos ExpressRoute virtuales son redundantes globalmente y seguirán las prácticas de enrutamiento BGP estándar. Por este motivo, recomendamos dos circuitos físicos por salida al proveedor en una configuración activa/activa.

Consulte la [página de preguntas más frecuentes](/azure/expressroute/expressroute-faqs) para obtener más información sobre los servicios admitidos, los costos y los detalles de configuración. Consulte el [artículo Ubicaciones de ExpressRoute](/azure/expressroute/expressroute-locations) para obtener información sobre la lista de proveedores de conectividad que ofrecen compatibilidad con el emparejamiento de Microsoft. También hemos grabado una serie de 10 partes de [Azure ExpressRoute para Office 365 Training](https://channel9.msdn.com/series/aer) en Channel 9 para ayudar a explicar los conceptos de forma más exhaustiva.
  
## <a name="ensuring-route-symmetry"></a>Garantizar la simetría de rutas

Los servidores front-end Office 365 son accesibles tanto en Internet como en ExpressRoute. Estos servidores prefieren enrutar de nuevo al entorno local a través de circuitos ExpressRoute cuando ambos estén disponibles. Por este motivo, existe la posibilidad de una asimetría de rutas si el tráfico de la red prefiere enrutar a través de los circuitos de Internet. Las rutas asimétricas son un problema porque los dispositivos que realizan la inspección de paquetes con estado pueden bloquear el tráfico devuelto que sigue una ruta de acceso diferente a los paquetes salientes seguidos.
  
Independientemente de si inicia una conexión a Office 365 a través de Internet o ExpressRoute, el origen debe ser una dirección enrutable públicamente. Con muchos clientes emparejando directamente con Microsoft, no es factible tener direcciones privadas donde sea posible la duplicación entre los clientes.
  
A continuación se muestran escenarios en los que se iniciarán las comunicaciones desde Office 365 a la red local. Para simplificar el diseño de red, se recomienda enrutar lo siguiente a través de la ruta de Acceso a Internet.
  
- Servicios SMTP, como correo de un inquilino de Exchange Online a un host local o correo de SharePoint Online enviado desde SharePoint Online a un host local. El protocolo SMTP se usa más ampliamente dentro de la red de Microsoft que los prefijos de ruta compartidos a través de circuitos ExpressRoute y la publicidad de servidores SMTP locales a través de ExpressRoute provocará errores con estos otros servicios.

- ADFS durante la validación de contraseñas para iniciar sesión.

- [Exchange Server implementaciones híbridas](/exchange/exchange-hybrid).

- [Búsqueda híbrida federada de SharePoint](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [BCS híbrido de SharePoint](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype Empresarial federación híbrida](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=/SkypeForBusiness/breadcrumb/toc.json&toc=/SkypeForBusiness/toc.json) o [Skype Empresarial](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype Empresarial Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Para que Microsoft vuelva a enrutar a la red para estos flujos de tráfico bidireccionales, las rutas BGP a los dispositivos locales deben compartirse con Microsoft. Al anunciar prefijos de ruta a Microsoft a través de ExpressRoute, debe seguir estos procedimientos recomendados:

1) No anuncie el mismo prefijo de ruta de dirección IP pública a Internet público y a través de ExpressRoute. Se recomienda que los anuncios de prefijo de ruta BGP ip para Microsoft a través de ExpressRoute procedan de un intervalo que no se anuncia a Internet en absoluto. Si esto no es posible lograr debido al espacio de direcciones IP disponible, es esencial asegurarse de que anuncia un intervalo más específico a través de ExpressRoute que cualquier circuito de Internet.

2) Use grupos de DIRECCIONES NAT independientes por circuito ExpressRoute y separados del de los circuitos de Internet.

3) Cualquier ruta anunciada a Microsoft atraerá el tráfico de red desde cualquier servidor de la red de Microsoft, no solo aquellas para las que se anuncian rutas a la red a través de ExpressRoute. Anuncie solo rutas a servidores en los que el equipo defina y comprenda bien los escenarios de enrutamiento. Anuncie prefijos de ruta de dirección IP independientes en cada uno de los varios circuitos ExpressRoute de la red.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Decidir qué aplicaciones y características enrutan a través de ExpressRoute

Al configurar una relación de emparejamiento mediante el dominio de enrutamiento de emparejamiento de Microsoft y se aprueba el acceso adecuado, podrá ver todos los servicios PaaS y SaaS disponibles a través de ExpressRoute. Los servicios de Office 365 diseñados para ExpressRoute se pueden administrar con [comunidades BGP](./bgp-communities-in-expressroute.md) o [filtros de ruta](/azure/expressroute/how-to-routefilter-portal).
  
Cada una de las características de Office 365 que están disponibles mediante el emparejamiento de Microsoft se enumeran en el [artículo puntos de conexión de Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) por tipo de aplicación y FQDN. La razón para usar el FQDN en las tablas es permitir a los clientes administrar el tráfico mediante archivos PAC u otras configuraciones de proxy, consulte nuestra guía para [administrar puntos de conexión de Office 365](./managing-office-365-endpoints.md) por ejemplo, archivos PAC.
  
En algunas situaciones, hemos usado un dominio comodín en el que uno o varios sub FQDN se anuncian de forma diferente al dominio comodín de nivel superior. Normalmente ocurre cuando el carácter comodín representa una larga lista de servidores que se anuncian en ExpressRoute e Internet, mientras que un pequeño subconjunto de destinos solo se anuncia en Internet o lo contrario. Consulte las tablas siguientes para comprender dónde están las diferencias.
  
En esta tabla se muestran los FQDN comodín que se anuncian en Internet y Azure ExpressRoute junto con los sub FQDN que se anuncian solo en Internet.

|**Dominio comodín anunciado en circuitos ExpressRoute e Internet**|**Sub-FQDN anunciado solo en circuitos de Internet**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Normalmente, los archivos PAC están diseñados para enviar solicitudes de red a puntos de conexión anunciados de ExpressRoute directamente al circuito y al resto de solicitudes de red al proxy. Si va a configurar un archivo PAC como este, cree el archivo PAC en el orden siguiente:
  
1. Incluya los sub FQDN de la columna dos de la tabla anterior en la parte superior del archivo PAC y envíe el tráfico hacia el proxy. Hemos creado un archivo PAC de ejemplo para que lo use en nuestro artículo sobre [la administración de puntos de conexión Office 365](./managing-office-365-endpoints.md).

2. Incluya todos los FQDN marcados como anunciados en ExpressRoute en [este artículo](./urls-and-ip-address-ranges.md) debajo de la primera sección y envíe el tráfico directamente al circuito ExpressRoute.

3. Incluya cualquier otro punto de conexión de red o reglas debajo de estas dos entradas, enviando el tráfico hacia el proxy.

En esta tabla se muestran los dominios comodín que se anuncian en circuitos de Internet solo junto con los sub FQDN que se anuncian en Azure ExpressRoute y circuitos de Internet. Para el archivo PAC anterior, los FQDN de la columna 2 de la tabla siguiente se muestran como anunciados en ExpressRoute en el vínculo al que se hace referencia, lo que significa que se incluirían en el segundo grupo de entradas del archivo.

|**Dominio comodín anunciado solo a circuitos de Internet**|**Sub FQDN anunciado en circuitos ExpressRoute e Internet**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> www.office.com  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |Outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover-\<tenant\>.outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Enrutamiento Office 365 tráfico a través de Internet y ExpressRoute

Para enrutar a la aplicación Office 365 que elija, deberá determinar una serie de factores clave.
  
1. Cuánto ancho de banda necesitará la aplicación. El muestreo del uso existente es el único método confiable para determinar esto en su organización.

2. De qué ubicación o ubicaciones de salida desea que salga el tráfico de red. Debe planear minimizar la latencia de red para la conectividad a Office 365, ya que esto afectará al rendimiento. Dado que Skype Empresarial usa vídeo y voz en tiempo real, es susceptible a una latencia de red deficiente.

3. Si desea que todas las ubicaciones de red o un subconjunto de ellas usen ExpressRoute.

4. Desde qué ubicaciones ofrece ExpressRoute el proveedor de red elegido.

Una vez que determine las respuestas a estas preguntas, puede aprovisionar un circuito ExpressRoute que satisfaga las necesidades de ancho de banda y ubicación. Para obtener más ayuda para el planeamiento de la red, consulte la [guía de optimización de red Office 365](./network-planning-and-performance.md) y el [caso práctico sobre cómo Microsoft controla el planeamiento del rendimiento de la red](https://aka.ms/tunemsit).
  
### <a name="example-1-single-geographic-location"></a>Ejemplo 1: Ubicación geográfica única
  
Este ejemplo es un escenario para una empresa ficticia llamada Trey Research que tiene una única ubicación geográfica.
  
Los empleados de Trey Research solo pueden conectarse a los servicios y sitios web en Internet que el departamento de seguridad permite explícitamente en el par de servidores proxy salientes que se encuentran entre la red corporativa y su ISP.
  
Trey Research planea usar Azure ExpressRoute para Office 365 y reconoce que algún tráfico, como el tráfico destinado a redes de entrega de contenido, no podrá enrutarse a través de ExpressRoute para Office 365 conexión. Dado que todo el tráfico ya se enruta a los dispositivos proxy de forma predeterminada, estas solicitudes seguirán funcionando como antes. Una vez que Trey Research determine que pueden cumplir los requisitos de enrutamiento de Azure ExpressRoute, proceden a crear un circuito, configurar el enrutamiento y vincular el nuevo circuito ExpressRoute a una red virtual. Una vez que se ha implementado la configuración fundamental de Azure ExpressRoute, Trey Research usa el [archivo PAC n.º 2 que publicamos](./managing-office-365-endpoints.md) para enrutar el tráfico con datos específicos del cliente a través de ExpressRoute directo para conexiones Office 365.
  
Como se muestra en el diagrama siguiente, Trey Research puede satisfacer el requisito de enrutar Office 365 tráfico a través de Internet y un subconjunto de tráfico a través de ExpressRoute mediante una combinación de cambios de configuración de proxy de enrutamiento y salida.
  
1. Con el [archivo PAC n.º 2 que publicamos](./managing-office-365-endpoints.md) para enrutar el tráfico a través de un punto de salida de Internet independiente para Azure ExpressRoute para Office 365.

2. Los clientes se configuran con una ruta predeterminada hacia los servidores proxy de Trey Research.

En este escenario de ejemplo, Trey Research usa un dispositivo proxy de salida. Del mismo modo, los clientes que no usan Azure ExpressRoute para Office 365 pueden querer usar esta técnica para enrutar el tráfico en función del costo de inspeccionar el tráfico destinado a puntos de conexión de alto volumen conocidos.
  
Los FQDN de volumen más altos para Exchange Online, SharePoint Online y Skype Empresarial Online son los siguientes:
  
![Red perimetral del cliente de ExpressRoute.](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\>-my.sharepoint.com, \<tenant-name\>-\<app\>.sharepoint.com

- \*.Lync.com junto con los intervalos IP para el tráfico que no es TCP

- \*broadcast.officeapps.live.com, \*excel.officeapps.live.com, \*onenote.officeapps.live.com, \*powerpoint.officeapps.live.com, \*view.officeapps.live.com, \*visio.officeapps.live.com, \*word-edit.officeapps.live.com, \*word-view.officeapps.live.com, office.live.com

Obtenga más información sobre [cómo implementar y administrar la configuración del proxy en Windows 8](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) y [asegurarse de que el proxy no limita Office 365](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx).
  
Con un único circuito ExpressRoute, no hay alta disponibilidad para Trey Research. En el caso de que se produzca un error en el par redundante de dispositivos perimetrales de Trey que atienden la conectividad de ExpressRoute, no hay un circuito ExpressRoute adicional al que conmutar por error. Esto deja a Trey Research en un predicado, ya que la conmutación por error a Internet requerirá una reconfiguración manual y, en algunos casos, nuevas direcciones IP. Si Trey quiere agregar alta disponibilidad, la solución más sencilla es agregar circuitos ExpressRoute adicionales para cada ubicación y configurar los circuitos de forma activa/activa.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Enrutamiento de ExpressRoute para Office 365 con varias ubicaciones

El último escenario, el enrutamiento Office 365 tráfico a través de ExpressRoute es la base para una arquitectura de enrutamiento aún más compleja. Independientemente del número de ubicaciones, el número de continentes en los que existen esas ubicaciones, el número de circuitos ExpressRoute, etc., será necesario poder enrutar algún tráfico a Internet y algún tráfico a través de ExpressRoute.
  
Las preguntas adicionales que se deben responder a los clientes con varias ubicaciones en varias zonas geográficas incluyen:
  
1. ¿Necesita un circuito ExpressRoute en todas las ubicaciones? Si usa Skype Empresarial Online o está preocupado por la confidencialidad de latencia para SharePoint Online o Exchange Online, se recomienda un par redundante de circuitos ExpressRoute activos o activos en cada ubicación. Consulte la guía de conectividad de red y calidad de los medios de Skype Empresarial para obtener más información.

2. Si un circuito ExpressRoute no está disponible en una región determinada, ¿cómo se debe enrutar Office 365 tráfico destinado?

3. ¿Cuál es el método preferido para consolidar el tráfico en el caso de redes con muchas ubicaciones pequeñas?

Cada uno de ellos presenta un desafío único que requiere que evalúe su propia red y las opciones disponibles de Microsoft.

|**Consideración**|**Componentes de red que se van a evaluar**|
|:-----|:-----|
|Circuitos en más de una ubicación  <br/> |Se recomienda un mínimo de dos circuitos configurados de forma activa/activa.  <br/> Se deben comparar las necesidades de costo, latencia y ancho de banda.  <br/> Use el costo de ruta BGP, los archivos PAC y NAT para administrar el enrutamiento con varios circuitos.  <br/> |
|Enrutamiento desde ubicaciones sin un circuito ExpressRoute  <br/> |Se recomienda la salida y la resolución dns tan cerca de la persona que inicia la solicitud de Office 365.  <br/> El reenvío DNS se puede usar para permitir que las oficinas remotas detecten el punto de conexión adecuado.  <br/> Los clientes de la oficina remota deben tener una ruta disponible que proporcione acceso al circuito ExpressRoute.  <br/> |
|Consolidación de oficinas pequeñas  <br/> |El ancho de banda disponible y el uso de datos deben compararse cuidadosamente.  <br/> |

> [!NOTE]
> Microsoft prefiere ExpressRoute sobre Internet si la ruta está disponible independientemente de la ubicación física.
  
Cada una de estas consideraciones debe tenerse en cuenta para cada red única. A continuación se muestra un ejemplo.
  
### <a name="example-2-multi-geographic-locations"></a>Ejemplo 2: Ubicaciones geográficas múltiples
  
Este ejemplo es un escenario para una empresa ficticia denominada "Humongous Insurance" que tiene varias ubicaciones geográficas.
  
Humongous Insurance está geográficamente disperso con oficinas en todo el mundo. Quieren implementar Azure ExpressRoute para Office 365 para mantener la mayoría de su tráfico Office 365 en conexiones de red directas. Humongous Insurance también tiene oficinas en otros dos continentes. Los empleados de la oficina remota en la que ExpressRoute no es factible deberán enrutar de vuelta a una o ambas instalaciones principales para usar una conexión ExpressRoute.
  
El principio rector es obtener Office 365 tráfico destinado a un centro de datos de Microsoft lo antes posible. En este ejemplo, Humongous Insurance debe decidir si sus oficinas remotas deben enrutarse a través de Internet para llegar a un centro de datos de Microsoft a través de cualquier conexión lo antes posible o si sus oficinas remotas deben enrutarse a través de una red interna para llegar a un centro de datos de Microsoft a través de una conexión ExpressRoute lo antes posible.
  
Los centros de datos, las redes y la arquitectura de aplicaciones de Microsoft están diseñados para tomar comunicaciones dispares globalmente y atenderlas de la manera más eficaz posible. Esta es una de las redes más grandes del mundo. Las solicitudes destinadas a Office 365 que permanecen en las redes del cliente más tiempo de lo necesario no podrán aprovechar esta arquitectura.
  
En la situación de Humongous Insurance, deben continuar en función de las aplicaciones que pretenden usar a través de ExpressRoute. Por ejemplo, si es un cliente de Skype Empresarial Online o planea usar la conectividad de ExpressRoute al conectarse a reuniones externas Skype Empresarial Online, el diseño recomendado en la guía de conectividad de red y calidad multimedia en línea de Skype Empresarial consiste en aprovisionar un circuito ExpressRoute adicional para la tercera ubicación. . Esto puede ser más costoso desde una perspectiva de red; sin embargo, el enrutamiento de solicitudes de un continente a otro antes de entregarse a un centro de datos de Microsoft puede provocar una experiencia deficiente o inutilizable durante Skype Empresarial reuniones y comunicaciones en línea.
  
Si Humongous Insurance no usa o no planea usar Skype Empresarial Online de ninguna manera, el enrutamiento Office 365 tráfico de red destinado de vuelta a un continente con una conexión ExpressRoute puede ser factible, aunque puede provocar latencia innecesaria o congestión tcp. En ambos casos, se recomienda enrutar el tráfico destinado a Internet a Internet en el sitio local para aprovechar las redes de entrega de contenido en las que se basa Office 365.
  
![Geografía múltiple de ExpressRoute.](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Cuando Humongous Insurance está planeando su estrategia de geografía múltiple, hay muchas cosas que tener en cuenta en torno al tamaño del circuito, el número de circuitos, la conmutación por error, etc.
  
Con ExpressRoute en una sola ubicación con varias regiones que intentan usar el circuito, Humongous Insurance quiere asegurarse de que las conexiones a Office 365 desde la oficina remota se envían a la sede central más cercana del centro de datos de Office 365 y las recibe la ubicación de la sede central. Para ello, Humongous Insurance implementa el reenvío DNS para reducir el número de ida y vuelta y búsquedas dns necesarias para establecer la conexión adecuada con el entorno de Office 365 más cercano al punto de salida de Internet de la sede central. Esto impide que el cliente resuelva un servidor front-end local y garantiza que el Front-End servidor al que se conecta la persona esté cerca de la sede central donde Humongous Insurance está emparejando con Microsoft. También puede aprender a [asignar un reenviador condicional para un nombre de dominio](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10)).
  
En este escenario, el tráfico de la oficina remota resolvería la infraestructura de front-end Office 365 en Norteamérica y usaría Office 365 para conectarse a los servidores back-end según la arquitectura de la aplicación Office 365. Por ejemplo, Exchange Online terminaría la conexión en Norteamérica y esos servidores front-end se conectarían al servidor de buzón de back-end dondequiera que residiera el inquilino. Todos los servicios tienen un servicio front door ampliamente distribuido compuesto por destinos unicast y anycast.
  
Si Humongous tiene oficinas principales en varios continentes, se recomienda un mínimo de dos circuitos activos/activos por región para reducir la latencia de aplicaciones confidenciales como Skype Empresarial Online. Si todas las oficinas están en un solo continente o no usan la colaboración en tiempo real, tener un punto de salida consolidado o distribuido es una decisión específica del cliente. Cuando hay varios circuitos disponibles, el enrutamiento BGP garantizará la conmutación por error en caso de que un único circuito deje de estar disponible.
  
Obtenga más información sobre [las configuraciones de enrutamiento de](/azure/expressroute/expressroute-config-samples-routing) ejemplo y [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat).
  
## <a name="selective-routing-with-expressroute"></a>Enrutamiento selectivo con ExpressRoute

El enrutamiento selectivo con ExpressRoute puede ser necesario por diversos motivos, como pruebas, la implementación de ExpressRoute en un subconjunto de usuarios. Hay varias herramientas que los clientes pueden usar para enrutar selectivamente Office 365 tráfico de red a través de ExpressRoute:
  
1. **Filtrado o segregación** de rutas: permite que las rutas BGP Office 365 a través de ExpressRoute a un subconjunto de subredes o enrutadores. Esto se enruta de forma selectiva por segmento de red de cliente o ubicación de oficina física. Esto es común para el lanzamiento escalonado de ExpressRoute para Office 365 y está configurado en los dispositivos BGP.

2. **Archivos o direcciones URL de PAC**: dirigir Office 365 tráfico de red destinado para fqdN específicos para enrutar en una ruta de acceso específica. Esto enruta de forma selectiva por equipo cliente tal como se identifica mediante la [implementación de archivos PAC](./managing-office-365-endpoints.md).

3. **Filtrado de rutas** -  [Los filtros de ruta](/azure/expressroute/how-to-routefilter-portal) son una manera de consumir un subconjunto de servicios admitidos a través del emparejamiento de Microsoft.

4. **Comunidades de BGP**: el filtrado basado en [etiquetas de comunidad BGP](./bgp-communities-in-expressroute.md) permite a un cliente determinar qué aplicaciones Office 365 atravesarán ExpressRoute y cuáles atravesarán Internet.

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>Temas relacionados

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)
  
[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimización de la red para Skype Empresarial Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute y calidad del servicio en Skype Empresarial Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flujo de llamadas con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Uso de comunidades BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)
