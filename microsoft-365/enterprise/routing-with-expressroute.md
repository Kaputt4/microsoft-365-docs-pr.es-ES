---
title: Enrutamiento con ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: En este artículo, obtenga información sobre los requisitos de enrutamiento, circuitos y dominios de enrutamiento de Azure ExpressRoute para su uso con Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693686"
---
# <a name="routing-with-expressroute-for-office-365"></a>Enrutamiento con ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para comprender correctamente el tráfico de enrutamiento a Office 365 con Azure ExpressRoute, necesitará comprender con firmeza los requisitos principales de enrutamiento de [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-routing/) y los circuitos y dominios de enrutamiento de [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/) Estos se basan en los conceptos básicos para usar ExpressRoute en el que confiarán los clientes de Office 365.
  
Algunos de los elementos clave de los artículos anteriores que deberá comprender son:
  
- Los circuitos de ExpressRoute no se asignan a una infraestructura física específica, pero son una conexión lógica realizada en una única ubicación de emparejamiento por Microsoft y un proveedor de emparejamiento en su nombre.

- Hay una asignación 1:1 entre un circuito de ExpressRoute y una clave de cliente.

- Cada circuito puede admitir 2 relaciones de emparejamiento independientes (emparejamiento privado de Azure y emparejamiento de Microsoft); Office 365 requiere emparejamiento de Microsoft.

- Cada circuito tiene un ancho de banda fijo que se comparte en todas las relaciones de emparejamiento.

- Todas las direcciones IPv4 públicas y los números AS públicos que se usarán para el circuito de ExpressRoute deben validarse como propiedad de usted o ser asignados exclusivamente por el propietario del intervalo de direcciones.

- Los circuitos virtuales de ExpressRoute son redundantes globalmente y seguirán las prácticas de enrutamiento BGP estándar. Por este motivo, se recomiendan dos circuitos físicos por salida a su proveedor en una configuración activa/activa.

Vea la página [de preguntas más frecuentes](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) para obtener más información sobre los servicios admitidos, los costos y los detalles de configuración. Consulte el artículo [de ubicaciones de ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para obtener información sobre la lista de proveedores de conectividad que ofrecen compatibilidad con emparejamiento de Microsoft. También hemos grabado una serie de aprendizaje de Azure ExpressRoute para [Office 365](https://channel9.msdn.com/series/aer) de 10 partes en Channel 9 para ayudar a explicar los conceptos de forma más exhaustiva.
  
## <a name="ensuring-route-symmetry"></a>Garantizar la simetría de rutas

Los servidores front-end de Office 365 son accesibles tanto en Internet como en ExpressRoute. Estos servidores prefieren enrutar de vuelta a la implementación local a través de circuitos de ExpressRoute cuando ambos estén disponibles. Por este problema, existe la posibilidad de una asimetría de rutas si el tráfico de la red prefiere enrutar por los circuitos de Internet. Las rutas asimétricas son un problema porque los dispositivos que realizan una inspección de paquetes con estado pueden bloquear el tráfico devuelto que sigue una ruta diferente de los paquetes salientes seguidos.
  
Independientemente de si inicia una conexión a Office 365 a través de Internet o ExpressRoute, el origen debe ser una dirección enrutable públicamente. Con muchos clientes emparejando directamente con Microsoft, no es factible tener direcciones privadas donde la duplicación sea posible entre los clientes.
  
Los siguientes son escenarios en los que se iniciarán las comunicaciones desde Office 365 a la red local. Para simplificar el diseño de red, se recomienda enrutar a través de la ruta de Acceso a Internet.
  
- Servicios SMTP, como correo de un inquilino de Exchange Online a un host local o correo de SharePoint Online enviado desde SharePoint Online a un host local. El protocolo SMTP se usa de forma más amplia dentro de la red de Microsoft que los prefijos de ruta compartidos a través de circuitos de ExpressRoute y la publicidad de servidores SMTP locales a través de ExpressRoute provocará errores con estos otros servicios.

- ADFS durante la validación de contraseña para el inicio de sesión.

- [Exchange Server implementaciones híbridas.](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)

- [Búsqueda híbrida federada de SharePoint.](https://technet.microsoft.com/library/dn197174.aspx)

- [BCS híbrido de SharePoint.](https://technet.microsoft.com/library/dn197239.aspx )

- [Skype Empresarial híbrido o](https://technet.microsoft.com/library/jj205403.aspx) federación [de Skype Empresarial.](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx)

- [Skype Empresarial Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

Para que Microsoft enruta de vuelta a la red para estos flujos de tráfico bidireccionales, las rutas BGP a los dispositivos locales deben compartirse con Microsoft. Al anunciar prefijos de ruta a Microsoft a través de ExpressRoute, debe seguir estos procedimientos recomendados:

1) No anuncie el mismo prefijo de ruta de dirección IP pública a Internet público y a través de ExpressRoute. Se recomienda encarecidamente que los anuncios de prefijo de ruta DE BGP IP para Microsoft a través de ExpressRoute sean de un rango que no se anuncia en Internet en absoluto. Si esto no es posible lograr debido al espacio de direcciones IP disponible, es esencial asegurarse de que anuncia un intervalo más específico a través de ExpressRoute que cualquier circuito de Internet.

2) Use grupos DE DIRECCIONES IP NAT independientes por circuito de ExpressRoute e independientes de los circuitos de Internet.

3) Tenga en cuenta que cualquier ruta anunciada a Microsoft atraerá el tráfico de red de cualquier servidor de la red de Microsoft, no solo aquellas para las que se anuncian rutas a su red a través de ExpressRoute. Solo anuncie rutas a los servidores donde el equipo defina y entienda bien los escenarios de enrutamiento. Anuncie prefijos de ruta de dirección IP independientes en cada uno de los distintos circuitos de ExpressRoute de la red.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Decidir qué aplicaciones y características enrutan a través de ExpressRoute

Cuando configure una relación de emparejamiento mediante el dominio de enrutamiento de emparejamiento de Microsoft y se apruebe para el acceso adecuado, podrá ver todos los servicios PaaS y SaaS disponibles a través de ExpressRoute. Los servicios de Office 365 diseñados para ExpressRoute se pueden administrar con [comunidades BGP](https://aka.ms/bgpexpressroute365) o filtros [de ruta.](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal)
  
Otras aplicaciones, como Office 365 Video, son una aplicación de Office 365; Sin embargo, Office 365 Video se compone de tres componentes diferentes, el portal, el servicio de streaming y la red de entrega de contenido. El portal reside en SharePoint Online, el servicio de streaming reside en Azure Media Services y la red de entrega de contenido reside dentro de la red CDN de Azure. En la tabla siguiente se describen estos componentes.

|**Componente**|**Aplicación subyacente**|**¿Se incluye en la comunidad BGP de SharePoint Online?**|**Usar**|
|:-----|:-----|:-----|:-----|
|Portal de vídeo de Office 365  <br/> |SharePoint Online  <br/> |Sí  <br/> |Configuración, carga  <br/> |
|Servicio de streaming de vídeo de Office 365  <br/> |Servicios multimedia de Azure  <br/> |No  <br/> |Servicio de streaming, usado en caso de que el vídeo no esté disponible desde la red CDN  <br/> |
|Red de entrega de contenido de vídeo de Office 365  <br/> |Azure CDN  <br/> |No  <br/> |Origen principal de la descarga/streaming de vídeo. Obtenga más información sobre las redes de vídeo de [Office 365.](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e)  <br/> |

Cada una de las características de Office 365 que están disponibles con el emparejamiento de Microsoft se enumeran en el artículo de puntos de conexión de [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) por tipo de aplicación y FQDN. El motivo para usar el FQDN en las tablas es permitir que los clientes administren el tráfico mediante archivos PAC u otras configuraciones de proxy, consulte nuestra guía para administrar puntos de conexión de [Office 365,](https://aka.ms/manageo365endpoints) por ejemplo, archivos PAC.
  
En algunas situaciones, hemos usado un dominio comodín en el que uno o más FQDN secundario se anuncian de forma diferente que el dominio comodín de nivel superior. Esto suele ocurrir cuando el carácter comodín representa una larga lista de servidores que se anuncian a ExpressRoute e Internet, mientras que un pequeño subgrupo de destinos solo se anuncia a Internet o a la inversa. Consulte las tablas siguientes para comprender dónde están las diferencias.
  
En esta tabla se muestran los FQDN de caracteres comodín que se anuncian en Internet y Azure ExpressRoute junto con los FQDN que se anuncian solo en Internet.

|**Dominio comodín anunciado a ExpressRoute y circuitos de Internet**|**FQDN de subdominio anunciado solo a circuitos de Internet**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Normalmente, los archivos PAC están diseñados para enviar solicitudes de red a puntos de conexión anunciados de ExpressRoute directamente al circuito y todas las demás solicitudes de red al proxy. Si está configurando un archivo PAC como este, redacte el archivo PAC en el siguiente orden:
  
1. Incluya los suba fqdN de la columna dos de la tabla anterior en la parte superior del archivo PAC, enviando el tráfico hacia el proxy. Hemos creado un archivo PAC de ejemplo para que lo use en nuestro artículo sobre la administración de puntos de conexión de [Office 365.](https://aka.ms/manageexpressroute365)

2. Incluya todos los FQDN marcados [](https://aka.ms/o365endpoints) como anuncios de ExpressRoute en este artículo debajo de la primera sección, enviando el tráfico directamente al circuito de ExpressRoute.

3. Incluye cualquier otro punto de conexión de red o reglas debajo de estas dos entradas, enviando el tráfico hacia el proxy.

En esta tabla se muestran los dominios comodín que se anuncian en circuitos de Internet solo junto con los fqdN secundarios que se anuncian a Azure ExpressRoute y a los circuitos de Internet. Para el archivo PAC anterior, los FQDN de la columna dos de la tabla siguiente aparecen como anunciados para ExpressRoute en el vínculo al que se hace referencia, lo que significa que se incluirían en el segundo grupo de entradas del archivo.

|**Dominio comodín anunciado solo para circuitos de Internet**|**Sub FQDN anunciado a ExpressRoute y circuitos de Internet**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Enrutamiento del tráfico de Office 365 a través de Internet y ExpressRoute

Para enrutar a la aplicación de Office 365 que elija tendrá que determinar una serie de factores clave.
  
1. Cantidad de ancho de banda que necesitará la aplicación. El muestreo del uso existente es el único método confiable para determinarlo en la organización.

2. Desde qué ubicación de salida quieres que el tráfico de red salga de la red. Debe planear minimizar la latencia de red para la conectividad a Office 365, ya que esto afectará al rendimiento. Como Skype Empresarial usa voz y vídeo en tiempo real, es particularmente susceptible a una latencia de red deficiente.

3. Si desea que todas o un subconjunto de las ubicaciones de red aprovechen ExpressRoute.

4. Desde qué ubicaciones ofrece ExpressRoute el proveedor de red elegido.

Una vez que determine las respuestas a estas preguntas, puede aprovisionar un circuito de ExpressRoute que satisfaga las necesidades de ancho de banda y ubicación. Para obtener más asistencia para planear la red, consulte la guía de ajuste de red de [Office 365](https://aka.ms/tune) y el caso práctico sobre cómo Microsoft controla la planeación del [rendimiento de la red.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>Ejemplo 1: Ubicación geográfica única
  
Este ejemplo es un escenario para una compañía ficticia llamada Trey Research que tiene una única ubicación geográfica.
  
Los empleados de Trey Research solo pueden conectarse a los servicios y sitios web de Internet que el departamento de seguridad permite explícitamente en el par de servidores proxy salientes que se encuentran entre la red corporativa y su ISP.
  
Trey Research planea usar Azure ExpressRoute para Office 365 y reconoce que algunos tráficos, como el tráfico destinado a redes de entrega de contenido, no podrán enrutar a través de la conexión de ExpressRoute para Office 365. Dado que todo el tráfico ya se enruta a los dispositivos proxy de forma predeterminada, estas solicitudes seguirán funcionando como antes. Después de que Trey Research determine que pueden cumplir los requisitos de enrutamiento de Azure ExpressRoute, proceden a crear un circuito, configurar el enrutamiento y vincular el nuevo circuito de ExpressRoute a una red virtual. Una vez que se haya hecho la configuración fundamental de Azure ExpressRoute, Trey Research usa el archivo PAC de #2 que publicamos para enrutar el tráfico con datos específicos del cliente [a](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) través de ExpressRoute directo para conexiones de Office 365.
  
Como se muestra en el siguiente diagrama, Trey Research puede satisfacer el requisito de enrutar el tráfico de Office 365 a través de Internet y un subconjunto de tráfico a través de ExpressRoute mediante una combinación de cambios de configuración de proxy de enrutamiento y salida.
  
1. Con el [#2 PAC que](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) publicamos para enrutar el tráfico a través de un punto de salida de Internet independiente para Azure ExpressRoute para Office 365.

2. Los clientes se configuran con una ruta predeterminada hacia los servidores proxy de Trey Research.

En este escenario de ejemplo, Trey Research usa un dispositivo proxy saliente. De forma similar, es posible que los clientes que no usen Azure ExpressRoute para Office 365 quieran usar esta técnica para enrutar el tráfico en función del costo de inspeccionar el tráfico destinado a puntos de conexión de gran volumen conocidos.
  
Los FQDN de mayor volumen para Exchange Online, SharePoint Online y Skype Empresarial Online son los siguientes:
  
![Red perimetral de cliente de ExpressRoute](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com junto con los intervalos IP para el tráfico no TCP

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* view.officeapps.live.com, \* visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Obtenga más información sobre cómo implementar y administrar la configuración de proxy en [Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) y asegurarse de que [Office 365](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)no esté limitada por el proxy.
  
Con un único circuito de ExpressRoute, no hay alta disponibilidad para Trey Research. En caso de que se produzca un error en el par redundante de dispositivos perimetrales de Trey que están atendiendo la conectividad de ExpressRoute, no hay un circuito de ExpressRoute adicional al que realizar la conmutación por error. Esto deja a Trey Research en un predicado, ya que la con error en Internet requerirá una nueva configuración manual y, en algunos casos, nuevas direcciones IP. Si Trey desea agregar alta disponibilidad, la solución más sencilla es agregar circuitos de ExpressRoute adicionales para cada ubicación y configurar los circuitos de forma activa/activa.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Enrutamiento de ExpressRoute para Office 365 con varias ubicaciones

El último escenario, el enrutamiento del tráfico de Office 365 a través de ExpressRoute es la base para una arquitectura de enrutamiento aún más compleja. Independientemente del número de ubicaciones, el número de continentes donde existen esas ubicaciones, el número de circuitos de ExpressRoute, y así sucesivamente, será necesario poder enrutar parte del tráfico a Internet y cierto tráfico a través de ExpressRoute.
  
Las preguntas adicionales que deben responderse a los clientes con varias ubicaciones en varias ubicaciones geográficas incluyen:
  
1. ¿Necesita un circuito de ExpressRoute en cada ubicación? Si usa Skype Empresarial Online o le preocupa la confidencialidad de latencia para SharePoint Online o Exchange Online, se recomienda un par redundante de circuitos de ExpressRoute activo/activo en cada ubicación. Consulte la guía de conectividad de red y calidad de medios de Skype Empresarial para obtener más información.

2. Si un circuito de ExpressRoute no está disponible en una región determinada, ¿cómo se debe enrutar el tráfico destinado a Office 365?

3. ¿Cuál es el método preferido para consolidar el tráfico en el caso de redes con muchas ubicaciones pequeñas?

Cada uno de estos presenta un desafío único que requiere que evalúe su propia red, así como las opciones disponibles de Microsoft.

|**Consideración**|**Componentes de red para evaluar**|
|:-----|:-----|
|Circuitos en más de una ubicación  <br/> |Se recomienda un mínimo de dos circuitos configurados de forma activa/activa.  <br/> Se deben comparar las necesidades de costo, latencia y ancho de banda.  <br/> Use el costo de ruta BGP, los archivos PAC y NAT para administrar el enrutamiento con varios circuitos.  <br/> |
|Enrutamiento desde ubicaciones sin un circuito de ExpressRoute  <br/> |Se recomienda la salida y la resolución DNS tan cerca de la persona que inicia la solicitud para Office 365.  <br/> El reenvío de DNS se puede usar para permitir que las oficinas remotas detecten el punto de conexión adecuado.  <br/> Los clientes de la oficina remota deben tener una ruta disponible que proporciona acceso al circuito de ExpressRoute.  <br/> |
|Consolidación de oficinas pequeñas  <br/> |El ancho de banda disponible y el uso de datos deben compararse cuidadosamente.  <br/> |

> [!NOTE]
> Microsoft prefiere ExpressRoute a través de Internet si la ruta está disponible independientemente de la ubicación física.
  
Cada una de estas consideraciones debe tenerse en cuenta para cada red única. A continuación se muestra un ejemplo.
  
### <a name="example-2-multi-geographic-locations"></a>Ejemplo 2: Ubicaciones multi geográficas
  
Este ejemplo es un escenario para una compañía ficticia denominada Humongous Insurance que tiene varias ubicaciones geográficas.
  
Humongous Insurance está geográficamente disperso con oficinas en todo el mundo. Quieren implementar Azure ExpressRoute para Office 365 para mantener la mayor parte del tráfico de Office 365 en conexiones de red directas. Humongous Insurance también tiene oficinas en dos continentes adicionales. Los empleados de la oficina remota en la que ExpressRoute no es viable tendrán que volver a enrutar a una o ambas instalaciones principales para usar una conexión de ExpressRoute.
  
El principio de orientación es obtener el tráfico destinado a Office 365 a un centro de datos de Microsoft lo más rápido posible. En este ejemplo, Humongous Insurance debe decidir si sus oficinas remotas deben enrutar a través de Internet para acceder a un centro de datos de Microsoft a través de cualquier conexión lo antes posible o si sus oficinas remotas deben enrutar a través de una red interna para llegar a un centro de datos de Microsoft a través de una conexión de ExpressRoute lo más rápido posible.
  
Los centros de datos, las redes y la arquitectura de aplicaciones de Microsoft están diseñados para tomar comunicaciones globales diferentes y dar servicio a ellas de la manera más eficaz posible. Se trata de una de las redes más grandes del mundo. Las solicitudes destinadas a Office 365 que permanecen en redes de clientes durante más tiempo del necesario no podrán aprovechar esta arquitectura.
  
En la situación de Humongous Insurance, deben continuar en función de las aplicaciones que pretenden usar en ExpressRoute. Por ejemplo, si es un cliente de Skype Empresarial Online o planea aprovechar la conectividad de ExpressRoute al conectarse a reuniones externas de Skype Empresarial Online, el diseño recomendado en la guía de conectividad de red y calidad de medios de Skype Empresarial Online es aprovisionar un circuito de ExpressRoute adicional para la tercera ubicación. Esto puede ser más caro desde el punto de vista de las redes; sin embargo, las solicitudes de enrutamiento de un continente a otro antes de entregar a un centro de datos de Microsoft pueden causar una experiencia deficiente o inutilizable durante las reuniones y comunicaciones de Skype Empresarial Online.
  
Si Humongous Insurance no usa o no planea aprovechar Skype Empresarial Online de ninguna manera, enrutar el tráfico de red destinado a Office 365 a un continente con una conexión de ExpressRoute puede ser viable, aunque puede causar latencia innecesaria o congestión TCP. En ambos casos, se recomienda enrutar el tráfico destinado a Internet a Internet en el sitio local para aprovechar las redes de entrega de contenido en las que se basa Office 365.
  
![Multi-geography de ExpressRoute](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Cuando Humongous Insurance planea su estrategia de varias zonas geográficas, hay una serie de aspectos que se deben tener en cuenta en torno al tamaño de los circuitos, el número de circuitos, la conmutación por error, entre otros.
  
Con ExpressRoute en una única ubicación con varias regiones que intentan usar el circuito, Humongous Insurance desea asegurarse de que las conexiones a Office 365 desde la oficina remota se envíen al centro de datos de Office 365 más cercano y se reciban en la ubicación de la sede central. Para ello, Humongous Insurance implementa el reenvío de DNS para reducir el número de recorridos de ida y vuelta y las búsquedas DNS necesarias para establecer la conexión adecuada con el entorno de Office 365 más cercano al punto de salida de Internet de la sede central. Esto impide que el cliente resuelva un servidor front-end local y garantiza que el servidor front-end al que se conecta la persona se encuentra cerca de la sede donde Humongous Insurance está interfirándose con Microsoft. También puede aprender a asignar [un reenviador condicional para un nombre de dominio.](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx)
  
En este escenario, el tráfico de la oficina remota resolvería la infraestructura front-end de Office 365 en Norteamérica y aprovecharía Office 365 para conectarse a los servidores back-end según la arquitectura de la aplicación de Office 365. Por ejemplo, Exchange Online finalizaría la conexión en Norteamérica y esos servidores front-end se conectarían al servidor de buzones back-end donde residía el inquilino. Todos los servicios tienen un servicio de puerta principal ampliamente distribuido formado por destinos de unidifusión y cualquier difusión.
  
Si Humongous tiene oficinas principales en varios continentes, se recomienda un mínimo de dos circuitos activos/activos por región para reducir la latencia de aplicaciones confidenciales como Skype Empresarial Online. Si todas las oficinas están en un solo continente o no usan la colaboración en tiempo real, tener un punto de salida consolidado o distribuido es una decisión específica del cliente. Cuando hay varios circuitos disponibles, el enrutamiento BGP garantizará la conmutación por error en caso de que un único circuito no esté disponible.
  
Obtenga más información sobre las configuraciones [de enrutamiento de ejemplo y](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Enrutamiento selectivo con ExpressRoute

El enrutamiento selectivo con ExpressRoute puede ser necesario por diversos motivos, como las pruebas, la aplicación de ExpressRoute a un subconjunto de usuarios. Hay varias herramientas que los clientes pueden usar para enrutar selectivamente el tráfico de red de Office 365 a través de ExpressRoute:
  
1. **Filtrado o segregación** de rutas: permitir que BGP enruta a Office 365 a través de ExpressRoute a un subconjunto de subredes o enrutadores. Esto se enruta selectivamente por segmento de red de cliente o ubicación de oficina física. Esto es común para escalonar la implementación de ExpressRoute para Office 365 y está configurado en sus dispositivos BGP.

2. **Direcciones URL/archivos PAC:** dirigir el tráfico de red destinado a Office 365 para fqdN específicos que se enrutar en una ruta específica. Esto enruta selectivamente por equipo cliente como se identifica mediante [la implementación de archivos PAC.](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies)

3. **Filtrado de rutas**  -  [Los filtros de](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) ruta son una forma de consumir un subconjunto de servicios admitidos a través del emparejamiento de Microsoft.

4. **Comunidades DE BGP:** el filtrado basado en etiquetas de la comunidad [BGP](https://aka.ms/bgpexpressroute365) permite al cliente determinar qué aplicaciones de Office 365 atravesarán ExpressRoute y cuáles atravesarán Internet.

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/erorouting](https://aka.ms/erorouting)
  
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
  
[Uso de comunidades de BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)
