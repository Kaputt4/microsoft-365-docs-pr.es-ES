---
title: Implementar ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: Obtenga información sobre cómo implementar ExpressRoute para Office 365, que proporciona una ruta de enrutamiento alternativa a muchos servicios Office 365 Internet.
ms.openlocfilehash: d75fe3a6dab4926babeef61fc14894566ff819b0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051371"
---
# <a name="implementing-expressroute-for-office-365"></a>Implementar ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

ExpressRoute para Office 365 proporciona una ruta de enrutamiento alternativa a muchos servicios Office 365 Internet. La arquitectura de ExpressRoute para Office 365 se basa en la publicidad de prefijos IP públicos de servicios de Office 365 que ya son accesibles a través de Internet en los circuitos de ExpressRoute aprovisionados para la redistribución posterior de esos prefijos IP en la red. Con ExpressRoute, habilita varias rutas de enrutamiento diferentes, a través de Internet y a través de ExpressRoute, para muchos Office 365 servicios. Este estado de enrutamiento en la red puede representar un cambio significativo en la forma en que se diseñó la topología de red interna.
  
 **Estado:** Guía completa v2
  
Debe planear cuidadosamente la implementación de ExpressRoute Office 365 para adaptarse a las complejidades de red de tener el enrutamiento disponible a través de un circuito dedicado con rutas inyectadas en la red principal e Internet. Si usted y su equipo no realizan la planeación y las pruebas detalladas de esta guía, existe un alto riesgo de que experimente una pérdida intermitente o total de conectividad a los servicios de Office 365 cuando el circuito de ExpressRoute esté habilitado.
  
Para tener una implementación correcta, deberá analizar los requisitos de la infraestructura, analizar la evaluación y el diseño detallados de la red, planear cuidadosamente el lanzamiento de forma controlada y por fases y crear un plan detallado de validación y pruebas. Para un entorno grande y distribuido, no es raro ver implementaciones que abarcan varios meses. Esta guía está diseñada para ayudarle a planear con antelación.
  
Las grandes implementaciones correctas pueden tardar seis meses en planearse y a menudo incluyen miembros del equipo de muchas áreas de la organización, incluidos los administradores de redes, firewalls y servidores proxy, administradores de Office 365, seguridad, soporte al usuario final, administración de proyectos y patrocinador ejecutivo. Su inversión en el proceso de planeación reducirá la probabilidad de que experimente errores de implementación que resulten en tiempo de inactividad o problemas complejos y costosos.
  
Esperamos que se completen los siguientes requisitos previos antes de iniciar esta guía de implementación.
  
1. Ha completado una evaluación de red para determinar si ExpressRoute se recomienda y aprueba.

2. Ha seleccionado un proveedor de servicios de red de ExpressRoute. Encuentre detalles sobre los partners [de ExpressRoute y las ubicaciones de emparejamiento.](/azure/expressroute/expressroute-locations)

3. Ya ha leído y entendido la documentación de [ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) y su red interna puede cumplir los requisitos previos de ExpressRoute de un extremo a otro.

4. Su equipo ha leído toda la guía pública y la documentación en , y ha visto la serie de aprendizaje de Azure ExpressRoute para Office 365 en canal 9 para obtener una comprensión de los detalles técnicos críticos, [https://aka.ms/expressrouteoffice365](./azure-expressroute.md) [https://aka.ms/ert](https://aka.ms/ert) como: [](https://channel9.msdn.com/series/aer)

      - Las dependencias de Internet de los servicios SaaS.

      - Cómo evitar rutas asimétricas y controlar el enrutamiento complejo.

      - Cómo incorporar controles de seguridad perimetral, disponibilidad y nivel de aplicación.

## <a name="begin-by-gathering-requirements"></a>Empezar por recopilar requisitos
<a name="requirements"> </a>

Empiece por determinar qué características y servicios tiene previsto adoptar dentro de su organización. Debe determinar qué características de los distintos servicios de Office 365 se usarán y qué ubicaciones de la red hospedarán a las personas que usan esas características. Con el catálogo de escenarios, debe agregar los atributos de red que cada uno de esos escenarios requiere; como los flujos de tráfico de red entrantes y salientes y si los Office 365 están disponibles a través de ExpressRoute o no.
  
Para recopilar los requisitos de la organización:
  
- Cataloge el tráfico de red entrante y saliente para los Office 365 que usa su organización. Consulte Office 365 de direcciones URL e intervalos de direcciones IP para obtener la descripción de los flujos que requieren Office 365 diferentes escenarios.

- Recopila documentación sobre la topología de red existente que muestra detalles de la topología y la red troncal WAN interna, la conectividad de sitios satélite, la conectividad de usuario de última milla, el enrutamiento a puntos de salida perimetral de red y los servicios proxy.

  - Identifique los puntos de conexión de servicio entrantes en los diagramas de red a los que se Office 365 y otros servicios Microsoft se conectarán, mostrando las rutas de conexión de Internet y ExpressRoute propuestas.

  - Identifique todas las ubicaciones de usuario geográficas y la conectividad WAN entre ubicaciones, junto con las ubicaciones con las que actualmente hay una salida a Internet y qué ubicaciones se propone que tengan una salida a una ubicación de emparejamiento de ExpressRoute.

  - Identifique todos los dispositivos perimetrales, como servidores proxy, firewalls, y así sucesivamente y cataloge su relación con los flujos que van a través de Internet y ExpressRoute.

  - Documente si los usuarios finales tendrán acceso Office 365 a través de enrutamiento directo o proxy indirecto de aplicaciones para flujos de Internet y ExpressRoute.

- Agregue la ubicación del inquilino y las ubicaciones de reunión al diagrama de red.

- Calcule las características de latencia y rendimiento de red esperados y observados desde las principales ubicaciones de usuario hasta Office 365. Tenga en cuenta que Office 365 es un conjunto global y distribuido de servicios y los usuarios se conectarán a ubicaciones que pueden ser diferentes de la ubicación de su inquilino. Por este motivo, se recomienda medir y optimizar la latencia entre el usuario y el borde más cercano de la red global de Microsoft a través de ExpressRoute y las conexiones a Internet. Puede usar los resultados de la evaluación de red para ayudar con esta tarea.

- Enumerar la seguridad de red de la empresa y los requisitos de alta disponibilidad que deben cumplirse con la nueva conexión de ExpressRoute. Por ejemplo, cómo los usuarios siguen teniendo acceso a Office 365 en caso de que se produce un error en la salida de Internet o el circuito de ExpressRoute.

- Documente qué flujos de red Office 365 entrantes y salientes usarán la ruta de acceso de Internet y cuáles usarán ExpressRoute. Los detalles específicos de las ubicaciones geográficas de los usuarios y los detalles de la topología de red local pueden requerir que el plan sea diferente de una ubicación de usuario a otra.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Catalogar el tráfico de red saliente y entrante
<a name="trafficCatalog"> </a>

Para minimizar el enrutamiento y otras complejidades de red, se recomienda usar ExpressRoute solo para Office 365 para los flujos de tráfico de red necesarios para pasar por una conexión dedicada debido a requisitos normativos o como resultado de la evaluación de red. Además, le recomendamos que escente el ámbito del enrutamiento de ExpressRoute y aborde los flujos de tráfico de red salientes y entrantes como distintas y distintas etapas del proyecto de implementación. Implementar ExpressRoute para Office 365 para flujos de tráfico de red salientes iniciados por el usuario y dejar flujos de tráfico de red entrantes a través de Internet puede ayudar a controlar el aumento de la complejidad topológica y los riesgos de introducir posibilidades de enrutamiento asimétrico adicionales.
  
El catálogo de tráfico de red debe contener listas de todas las conexiones de red entrantes y salientes que tendrá entre la red local y Microsoft.
  
- Los flujos de tráfico de red salientes son escenarios en los que se inicia una conexión desde el entorno local, como desde clientes o servidores internos, con un destino de la servicios Microsoft. Estas conexiones pueden ser directas Office 365 o indirectas, como cuando la conexión pasa por servidores proxy, firewalls u otros dispositivos de red en la ruta de acceso a Office 365.

- Los flujos de tráfico de red entrantes son escenarios en los que se inicia una conexión desde la nube de Microsoft a un host local. Por lo general, estas conexiones deben pasar por firewall y otra infraestructura de seguridad que la directiva de seguridad del cliente requiere para los flujos originados externamente.

Lea  la sección Garantizar la simetría de ruta del artículo Enrutamiento con [ExpressRoute](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) para Office 365 para determinar qué servicios enviarán tráfico entrante y buscar la columna marcada como **ExpressRoute para Office 365** en el artículo de referencia de extremos de [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar el resto de la información de conectividad.
  
Para cada servicio que requiera una conexión saliente, querrá describir la conectividad planeada para el servicio, incluido el enrutamiento de red, la configuración de proxy, la inspección de paquetes y las necesidades de ancho de banda.
  
Para cada servicio que requiera una conexión entrante, necesitará información adicional. Los servidores de la nube de Microsoft establecerán conexiones a la red local. para asegurarse de que las conexiones se realizan correctamente, querrá describir todos los aspectos de esta conectividad, incluidos; las entradas DNS públicas para los servicios que aceptarán estas conexiones entrantes, las direcciones IP IPv4 con formato CIDR, los equipos ISP implicados y la forma en que se administra NAT entrante o NAT de origen para estas conexiones.
  
Las conexiones entrantes deben revisarse independientemente de si se conectan a través de Internet o ExpressRoute para garantizar que no se haya introducido el enrutamiento asimétrico. En algunos casos, los puntos de conexión locales a los que los servicios Office 365 inician conexiones entrantes también pueden tener acceso otros microsoft y no servicios Microsoft. Es fundamental que habilitar el enrutamiento de ExpressRoute a estos servicios Office 365 no rompa otros escenarios. En muchos casos, es posible que los clientes necesiten implementar cambios específicos en su red interna, como NAT basada en origen, para garantizar que los flujos entrantes de Microsoft permanezcan simétricos después de habilitar ExpressRoute.
  
Este es un ejemplo del nivel de detalle requerido. En este caso, Exchange híbrido se enrutaría al sistema local a través de ExpressRoute.

|**Connection (propiedad)**|**Valor**|
|:-----|:-----|
|**Dirección del tráfico de red** <br/> |Entrada  <br/> |
|**Servicio** <br/> |Exchange Hybrid  <br/> |
|**Extremo Office 365 público (origen)** <br/> |Exchange Online (direcciones IP)  <br/> |
|**Extremo local público (destino)** <br/> |5.5.5.5  <br/> |
|**Entrada DNS pública (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**¿Este extremo local se usará para otros usuarios (que no Office 365) servicios Microsoft** <br/> |No  <br/> |
|**¿Los usuarios o sistemas de Internet usarán este extremo local?** <br/> |Sí  <br/> |
|**Sistemas internos publicados a través de puntos de conexión públicos** <br/> |Exchange Server de acceso de cliente (local) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**Anuncio DE IP del extremo público** <br/> |**Para Internet**: 5.5.0.0/16  <br/> **To ExpressRoute**: 5.5.5.0/24  <br/> |
|**Controles de seguridad/perímetro** <br/> |**Ruta de acceso a Internet:** DeviceID_002  <br/> **Ruta de acceso de ExpressRoute:** DeviceID_003  <br/> |
|**Alta disponibilidad** <br/> |Activo/Activo en 2 redundancia geográfica  <br/> Circuitos de ExpressRoute: Chicago y Dallas  <br/> |
|**Control de simetría de ruta** <br/> |**Método**: NAT de origen  <br/> **Ruta de acceso a Internet:** conexiones entrantes NAT de origen a 192.168.5.5  <br/> |Ruta de acceso **de ExpressRoute:** conexiones NAT de origen a 192.168.1.0 (Chicago) y 192.168.2.0 (Dallas)  <br/> |

Este es un ejemplo de un servicio que solo es saliente:

|**Connection (propiedad)**|**Valor**|
|:-----|:-----|
|**Dirección del tráfico de red** <br/> |Salida  <br/> |
|**Servicio** <br/> |SharePoint Online  <br/> |
|**Extremo local (origen)** <br/> |Estación de trabajo de usuario  <br/> |
|**Extremo Office 365 público (destino)** <br/> |SharePoint En línea (direcciones IP)  <br/> |
|**Entrada DNS pública (Internet)** <br/> |\*.sharepoint.com (y FQDN adicionales)  <br/> |
|**CDN Referencias** <br/> |cdn.sharepointonline.com (y FQDN adicionales): direcciones IP mantenidas por CDN proveedores)  <br/> |
|**Anuncio IP y NAT en uso** <br/> |**Ruta de acceso a Internet/NAT de** origen: 1.1.1.0/24  <br/> Ruta de acceso **de ExpressRoute/NAT** de origen: 1.1.2.0/24 (Chicago) y 1.1.3.0/24 (Dallas)  <br/> |
|**Método de conectividad** <br/> |**Internet:** a través del proxy de la capa 7 (archivo .pac)  <br/> **ExpressRoute:** enrutamiento directo (sin proxy)  <br/> |
|**Controles de seguridad/perímetro** <br/> |**Ruta de acceso a Internet:** DeviceID_002  <br/> **Ruta de acceso de ExpressRoute:** DeviceID_003  <br/> |
|**Alta disponibilidad** <br/> |**Ruta de acceso** a Internet: salida redundante de Internet  <br/> **Ruta de acceso de ExpressRoute:** enrutamiento activo/activo de "hot potato" a través de 2 circuitos de ExpressRoute con redundancia geográfica: Chicago y Dallas  <br/> |
|**Control de simetría de ruta** <br/> |**Método**: NAT de origen para todas las conexiones  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Diseño de topología de red con conectividad regional
<a name="topology"> </a>

Una vez que comprenda los servicios y sus flujos de tráfico de red asociados, puede crear un diagrama de red que incorpore estos nuevos requisitos de conectividad e ilustra los cambios que hará para usar ExpressRoute para Office 365. El diagrama debe incluir:
  
1. Todas las ubicaciones de usuario desde Office 365 y otros servicios.

2. Todos los puntos de salida de Internet y ExpressRoute.

3. Todos los dispositivos salientes y entrantes que administran la conectividad dentro y fuera de la red, incluidos enrutadores, firewalls, servidores proxy de aplicaciones y detección y prevención de intrusiones.

4. Destinos internos para todo el tráfico entrante, como servidores ADFS internos que aceptan conexiones desde los servidores proxy de aplicación web de ADFS.

5. Catálogo de todas las subredes IP que se anunciarán

6. Identifique cada ubicación en la que las personas accederán Office 365 y enumérme las ubicaciones de reunión que se usarán para ExpressRoute.

7. Ubicaciones y partes de la topología de red interna, donde se aceptarán, filtrarán y propagarán los prefijos IP de Microsoft aprendidos de ExpressRoute.

8. La topología de red debe ilustrar la ubicación geográfica de cada segmento de red y cómo se conecta a la red de Microsoft a través de ExpressRoute o Internet.

El diagrama siguiente muestra cada ubicación en la que las personas usarán Office 365 los anuncios de enrutamiento entrantes y salientes para Office 365.
  
![Reunión geográfica regional de ExpressRoute](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Para el tráfico saliente, el acceso de Office 365 de tres maneras:
  
1. A través de una ubicación de reunión en Norteamérica para los usuarios de California.

2. A través de una ubicación de reunión en Hong Kong para los usuarios de Hong Kong.

3. A través de Internet en Bangladesh donde hay menos personas y ningún circuito de ExpressRoute aprovisionado.

![Conexiones salientes para diagrama regional](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Del mismo modo, el tráfico de red entrante de Office 365 devuelve de tres maneras:
  
1. A través de una ubicación de reunión en Norteamérica para los usuarios de California.

2. A través de una ubicación de reunión en Hong Kong para los usuarios de Hong Kong.

3. A través de Internet en Bangladesh donde hay menos personas y ningún circuito de ExpressRoute aprovisionado.

![Conexiones entrantes para diagrama regional](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Determinar la ubicación de reunión adecuada

La selección de ubicaciones de reunión, que son la ubicación física desde la que el circuito de ExpressRoute conecta la red a la red de Microsoft, se ve influenciada por las ubicaciones desde las que los usuarios tendrán acceso Office 365 usuario. Como oferta de SaaS, Office 365 no funciona en el modelo regional de IaaS o PaaS del mismo modo que Lo hace Azure. En su lugar, Office 365 es un conjunto distribuido de servicios de colaboración, donde es posible que los usuarios necesiten conectarse a puntos de conexión en varios centros de datos y regiones, que puede que no necesariamente esté en la misma ubicación o región donde se hospeda el inquilino del usuario.
  
Esto significa que la consideración más importante que debe tener en cuenta al seleccionar ubicaciones de reunión para ExpressRoute para Office 365 es desde dónde se conectarán las personas de su organización. La recomendación general para una conectividad Office 365 óptima es implementar el enrutamiento, de modo que las solicitudes de usuario a los servicios de Office 365 se entreguen en la red de Microsoft a través de la ruta de red más corta, lo que también suele denominarse enrutamiento de "hot potato". Por ejemplo, si la mayoría de los usuarios de Office 365 se encuentran en una o dos ubicaciones, seleccionar las ubicaciones de reunión que están más cerca de la ubicación de esos usuarios creará el diseño óptimo. Si su empresa tiene grandes poblaciones de usuarios en muchas regiones diferentes, es posible que desee considerar tener varios circuitos de ExpressRoute y ubicaciones de reunión. Para algunas de las ubicaciones de usuario, la ruta de acceso más corta o óptima a la red de Microsoft y Office 365, puede que no sea a través de la WAN interna y los puntos de reunión de ExpressRoute, sino a través de Internet.
  
A menudo, hay varias ubicaciones de reunión que podrían seleccionarse dentro de una región con una proximidad relativa a los usuarios. Rellene la tabla siguiente para guiar sus decisiones.

|**Ubicaciones de reunión de Planned ExpressRoute en California y Nueva York**||
|:-----|:-----|
|Ubicación  <br/> |Número de personas  <br/> |Latencia esperada en la red de Microsoft a través de la salida de Internet  <br/> |Latencia esperada en la red de Microsoft a través de ExpressRoute  <br/> |
|Los Ángeles  <br/> |10 000  <br/> |~15 ms  <br/> |~10ms (a través de Silicon Valley)  <br/> |
|Washington DC  <br/> |15 000  <br/> |~20ms  <br/> |~10ms (a través de Nueva York)  <br/> |
|Dallas  <br/> |5.000  <br/> |~15 ms  <br/> |~40ms (a través de Nueva York)  <br/> |

Una vez desarrollada la arquitectura de red global que muestra la región de Office 365, las ubicaciones de reunión del proveedor de servicios de red de ExpressRoute y la cantidad de personas por ubicación, se puede usar para identificar si se puede realizar alguna optimización. También puede mostrar conexiones de red de horquilla global en las que el tráfico se enruta a una ubicación lejana para obtener la ubicación de reunión. Si se detecta una horquilla en la red global, debe corregirse antes de continuar. Busque otra ubicación de reunión o use puntos de salida de interrupción selectiva de Internet para evitar la horquilla.
  
El primer diagrama muestra un ejemplo de un cliente con dos ubicaciones físicas en Norteamérica. Puede ver la información acerca de las ubicaciones de oficina, Office 365 de inquilinos y varias opciones para las ubicaciones de reunión de ExpressRoute. En este ejemplo, el cliente ha seleccionado la ubicación meet-me en función de dos principios, en orden:
  
1. Proximidad más cercana a las personas de su organización.

2. Más cerca de un centro de datos de Microsoft donde Office 365 está hospedado.

![ExpressRoute US geographic meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Expandiendo este concepto un poco más lejos, el segundo diagrama muestra un ejemplo de cliente multinacionales frente a información y toma de decisiones similares. Este cliente tiene una pequeña oficina en Bangladesh con un pequeño equipo de diez personas centrado en aumentar su superficie en la región. Hay una ubicación de reunión en Chennai y un centro de datos de Microsoft con Office 365 hospedado en Chennai para que una ubicación de reunión tenga sentido; sin embargo, para diez personas, el gasto del circuito adicional es gravoso. Al mirar la red, deberá determinar si la latencia que implica enviar el tráfico de red a través de la red es más eficaz que gastar el capital para adquirir otro circuito de ExpressRoute.
  
Como alternativa, las diez personas de Bangladesh pueden experimentar un mejor rendimiento con su tráfico de red enviado a través de Internet a la red de Microsoft que enrutar en su red interna, como mostramos en los diagramas introductorios y reproducimos a continuación.
  
![Conexiones salientes para diagrama regional](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Crear el plan de implementación de ExpressRoute Office 365 de implementación
<a name="implementation"> </a>

El plan de implementación debe incluir tanto los detalles técnicos de la configuración de ExpressRoute como los detalles de la configuración de toda la infraestructura de la red, como la siguiente.
  
- Planee qué servicios se dividen entre ExpressRoute e Internet.

- Planee el ancho de banda, la seguridad, la alta disponibilidad y la conmutación por error.

- Diseñar el enrutamiento entrante y saliente, incluidas las optimizaciones de ruta de enrutamiento adecuadas para diferentes ubicaciones

- Decida hasta dónde se anunciarán las rutas de ExpressRoute en la red y cuál es el mecanismo para que los clientes seleccionen la ruta de Acceso de Internet o ExpressRoute; por ejemplo, enrutamiento directo o proxy de aplicación.

- Planear cambios en los registros DNS, incluidas las entradas [del marco](../security/defender-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md) de directivas de remitente.

- Planeación de la estrategia NAT, incluido NAT de origen saliente y entrante.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Planear el enrutamiento con rutas de red de Internet y ExpressRoute
<a name="paths"> </a>

- Para la implementación inicial, se recomienda usar Internet para todos los servicios entrantes, como el correo electrónico entrante o la conectividad híbrida.

- Plan end user client LAN routing, such as [configuring a PAC/WPAD file,](./managing-office-365-endpoints.md)default route, proxy servers, and BGP route advertisements.

- Planee el enrutamiento perimetral, incluidos servidores proxy, firewalls y servidores proxy en la nube.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Planear el ancho de banda, la seguridad, la alta disponibilidad y la conmutación por error
<a name="availability"> </a>

Cree un plan para el ancho de banda necesario para cada carga de trabajo Office 365 principal. Calcule por separado Exchange Online, SharePoint online y Skype Empresarial de ancho de banda en línea. Puede usar las calculadoras de estimación que hemos proporcionado para Exchange Online y Skype Empresarial como punto de partida; sin embargo, se requiere una prueba piloto con una muestra representativa de los perfiles y ubicaciones de usuario para comprender completamente las necesidades de ancho de banda de su organización.
  
Agregue a su plan cómo se administra la seguridad en cada ubicación de salida de Internet y ExpressRoute, recuerde que todas las conexiones de ExpressRoute Office 365 usan emparejamiento público y debe protegerse de acuerdo con las directivas de seguridad de la empresa para conectarse a redes externas.
  
Agregue detalles al plan sobre qué personas se verán afectadas por el tipo de interrupción y cómo podrán realizar su trabajo a plena capacidad de la manera más sencilla.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Planear los requisitos de ancho de banda Skype Empresarial los requisitos de vibración, latencia, congestión y Headroom
  
Skype Empresarial Online también tiene requisitos de red adicionales específicos que se detallan en el artículo Calidad de medios y Rendimiento de conectividad de [red en Skype Empresarial Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).
  
Lea la sección **Planeación de ancho de banda para Azure ExpressRoute** en [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Al realizar una evaluación de ancho de banda con los usuarios piloto, puede usar nuestra guía; [Office 365 optimización del rendimiento mediante líneas base e historial de rendimiento](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).
  
#### <a name="plan-for-high-availability-requirements"></a>Planeación de requisitos de alta disponibilidad
  
Cree un plan de alta disponibilidad para satisfacer sus necesidades e incorpore esto en el diagrama de topología de red actualizado. Lea la sección **Alta disponibilidad y conmutación** por error con Azure ExpressRoute en Network planning with [ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
#### <a name="plan-for-network-security-requirements"></a>Planear los requisitos de seguridad de red
  
Cree un plan para cumplir los requisitos de seguridad de red e incorpore esto en el diagrama de topología de red actualizado. Lea la sección Aplicar controles de seguridad a **Azure ExpressRoute para** Office 365 escenarios de planificación de red con [ExpressRoute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Diseñar conectividad de servicio saliente
<a name="outbound"> </a>

ExpressRoute para Office 365 tiene *requisitos de* red salientes que pueden ser desconocidos. En concreto, las direcciones IP que representan a los usuarios y redes para Office 365 y actúan como puntos de conexión de origen para las conexiones de red salientes a Microsoft deben cumplir los requisitos específicos que se describen a continuación.
  
1. Los puntos de conexión deben ser direcciones IP públicas, registradas en su empresa o para la compañía que le proporcione conectividad a ExpressRoute.

2. ExpressRoute debe anunciar los puntos de conexión a Microsoft y validar o aceptar los puntos de conexión.

3. Los puntos de conexión no deben anunciarse en Internet con la misma o más métrica de enrutamiento preferida.

4. Los extremos no deben usarse para la conectividad a servicios Microsoft que no están configurados a través de ExpressRoute.

Si el diseño de red no cumple estos requisitos, existe un alto riesgo de que los usuarios experimenten errores de conectividad en Office 365 y otros servicios Microsoft debido a la enrutación de holing negro o el enrutamiento asimétrico. Esto ocurre cuando las solicitudes a servicios Microsoft se enrutan a través de ExpressRoute, pero las respuestas se enrutan de nuevo a través de Internet o viceversa, y los dispositivos de red con estado, como firewalls, descartan las respuestas.
  
El método más común que puede usar para cumplir los requisitos anteriores es usar NAT de origen, ya sea implementado como parte de la red o proporcionado por el proveedor de ExpressRoute. NAT de origen le permite abstraer los detalles y el direccionamiento IP privado de su red de Internet desde ExpressRoute y; junto con los anuncios de ruta IP adecuados, proporciona un mecanismo fácil para garantizar la simetría de la ruta. Si usa dispositivos de red con estado específicos para las ubicaciones de emparejamiento de ExpressRoute, debe implementar grupos NAT independientes para cada emparejamiento de ExpressRoute para garantizar la simetría de rutas.
  
Obtenga más información sobre los [requisitos de NAT de ExpressRoute.](/azure/expressroute/expressroute-nat)
  
Agregue los cambios para la conectividad saliente al diagrama de topología de red.
  
### <a name="design-inbound-service-connectivity"></a>Diseñar conectividad de servicio entrante
<a name="inbound"> </a>

La mayoría de las implementaciones de Office 365 de empresa suponen algún tipo de conectividad entrante de Office 365 a servicios locales, como para escenarios híbridos de Exchange, SharePoint y Skype Empresarial, migraciones de buzones y autenticación mediante infraestructura de ADFS. Cuando ExpressRoute habilita una ruta de enrutamiento adicional entre la red local y Microsoft para la conectividad saliente, estas conexiones entrantes pueden inadvertidamente resultar afectadas por el enrutamiento asimétrico, incluso si desea que esos flujos sigan usando Internet. Se recomiendan algunas precauciones que se describen a continuación para garantizar que no haya ningún impacto en los flujos de entrada basados en Internet desde Office 365 a sistemas locales.
  
Para minimizar los riesgos del enrutamiento asimétrico para los flujos de tráfico de red entrantes, todas las conexiones entrantes deben usar NAT de origen antes de enrutar a segmentos de la red que tienen visibilidad de enrutamiento en ExpressRoute. Si las conexiones entrantes se permiten en un segmento de red con visibilidad de enrutamiento en ExpressRoute sin NAT de origen, las solicitudes procedentes de Office 365 entrarán desde Internet, pero la respuesta que vuelva a Office 365 preferirá la ruta de red de ExpressRoute de vuelta a la red de Microsoft, lo que provocará un enrutamiento asimétrico.
  
Puede considerar uno de los siguientes patrones de implementación para satisfacer este requisito:
  
1. Realice NAT de origen antes de que las solicitudes se enruten a la red interna con equipos de red como firewalls o equilibradores de carga en la ruta de acceso de Internet a los sistemas locales.

2. Asegúrese de que las rutas de ExpressRoute no se propagan a los segmentos de red donde residen los servicios entrantes, como servidores front-end o sistemas proxy inversos, que administran las conexiones a Internet.

La contabilidad explícita de estos escenarios en la red y el mantenimiento de todos los flujos de tráfico de red entrantes a través de Internet ayuda a minimizar el riesgo operativo y de implementación del enrutamiento asimétrico.
  
Puede haber casos en los que puede optar por dirigir algunos flujos de entrada a través de conexiones de ExpressRoute. Para estos escenarios, tiene en cuenta las siguientes consideraciones adicionales.
  
1. Office 365 solo pueden dirigirse a puntos de conexión locales que usen IP públicas. Esto significa que, incluso si el punto de conexión de entrada local solo se expone a Office 365 a través de ExpressRoute, debe tener una IP pública asociada.

2. Todas las resoluciones de nombres DNS que Office 365 servicios realizan para resolver puntos de conexión locales se realizan mediante DNS público. Esto significa que debe registrar el FQDN de los extremos de servicio entrantes en las asignaciones IP en Internet.

3. Para recibir conexiones de red entrantes a través de ExpressRoute, las subredes IP públicas de estos extremos deben anunciarse a Microsoft a través de ExpressRoute.

4. Evalúe cuidadosamente estos flujos de tráfico de red entrantes para asegurarse de que se les aplican controles de seguridad y de red adecuados de acuerdo con las directivas de seguridad y red de su empresa.

5. Una vez que los puntos de conexión de entrada locales se anuncian en Microsoft a través de ExpressRoute, ExpressRoute se convertirá en la ruta de enrutamiento preferida a esos puntos de conexión para todos los servicios Microsoft, incluidos Office 365. Esto significa que esas subredes de extremo solo deben usarse para las comunicaciones con Office 365 servicios y ningún otro servicio en la red de Microsoft. De lo contrario, el diseño provocará un enrutamiento asimétrico en el que las conexiones entrantes de otras servicios Microsoft prefieran enrutar entrantes a través de ExpressRoute, mientras que la ruta de devolución usará Internet.

6. En el caso de que un circuito de ExpressRoute o una ubicación de reunión no esté disponible, deberá asegurarse de que los extremos de entrada locales siguen estando disponibles para aceptar solicitudes a través de una ruta de red independiente. Esto puede significar subredes de publicidad para esos puntos de conexión a través de varios circuitos de ExpressRoute.

7. Se recomienda aplicar NAT de origen para todos los flujos de tráfico de red entrantes que entran en la red a través de ExpressRoute, especialmente cuando estos flujos atraviesan dispositivos de red con estado, como firewalls.

8. Algunos servicios locales, como el proxy ADFS o la detección automática de Exchange, pueden recibir solicitudes entrantes tanto de los servicios Office 365 como de los usuarios de Internet. Para estas solicitudes, Office 365 se dirigirá al mismo FQDN que las solicitudes de usuario a través de Internet. Permitir conexiones de usuarios entrantes desde Internet a esos puntos de conexión locales, al tiempo que forzar Office 365 conexiones a usar ExpressRoute, representa una complejidad de enrutamiento significativa. Para la gran mayoría de los clientes que implementan estos escenarios complejos a través de ExpressRoute no se recomienda debido a consideraciones operativas. Esta sobrecarga adicional incluye la administración de riesgos de enrutamiento asimétrico y le exigirá administrar cuidadosamente los anuncios y directivas de enrutamiento en varias dimensiones.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Actualizar el plan de topología de red para mostrar cómo evitar rutas asimétricas
<a name="asymmetric"> </a>

Desea evitar el enrutamiento asimétrico para garantizar que los usuarios de su organización puedan usar sin problemas Office 365 y otros servicios importantes en Internet. Hay dos configuraciones comunes que tienen los clientes que provocan el enrutamiento asimétrico. Ahora es un buen momento para revisar la configuración de red que está planeando usar y comprobar si podría existir uno de estos escenarios de enrutamiento asimétrico.
  
Para empezar, examinaremos algunas situaciones diferentes asociadas con el siguiente diagrama de red. En este diagrama, todos los servidores que reciben solicitudes entrantes, como ADFS o servidores híbridos locales, están en el centro de datos de Nueva Jersey y se anuncian en Internet.
  
1. Aunque la red perimetral es segura, no hay nat de origen disponible para las solicitudes entrantes.

2. Los servidores del centro de datos de Nueva Jersey pueden ver las rutas de Internet y ExpressRoute.

![Introducción a la conectividad de ExpressRoute](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
También tenemos sugerencias sobre cómo corregirlas.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problema 1: conexión de nube a local a través de Internet
  
En el siguiente diagrama se muestra la ruta de acceso de red asimétrica que se toma cuando la configuración de red no proporciona NAT para las solicitudes entrantes de la nube de Microsoft a través de Internet.
  
1. La solicitud entrante de Office 365 recupera la dirección IP del extremo local del DNS público y envía la solicitud a la red perimetral.

2. En esta configuración defectuosa, no hay nat de origen configurada o disponible en la red perimetral donde se envía el tráfico, lo que da como resultado que la dirección IP de origen real se utilice como destino de devolución.

  - El servidor de la red enruta el tráfico devuelto a Office 365 a través de cualquier conexión de red de ExpressRoute disponible.

  - El resultado es una ruta asimétrica para que ese flujo Office 365, lo que da como resultado una conexión rota.

![Problema de enrutamiento asimétrico de ExpressRoute 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Solución 1a: NAT de origen
  
Simplemente agregar un NAT de origen a la solicitud entrante resuelve esta red mal configurada. En este diagrama:
  
1. La solicitud entrante continúa entrando a través de la red perimetral del centro de datos de Nueva Jersey. Esta vez nat de origen está disponible.

2. La respuesta del servidor se enruta de nuevo hacia la DIRECCIÓN IP asociada con nat de origen en lugar de la dirección IP original, lo que da como resultado que la respuesta vuelva a lo largo de la misma ruta de red.

![Solución de enrutamiento Asymetric de ExpressRoute 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Solución 1b: Ámbito de ruta
  
Como alternativa, puede optar por no permitir la publicidad de los prefijos BGP de ExpressRoute, quitando la ruta de acceso de red alternativa para esos equipos. En este diagrama:
  
1. La solicitud entrante continúa entrando a través de la red perimetral del centro de datos de Nueva Jersey. Esta vez, los prefijos anunciados desde Microsoft a través del circuito ExpressRoute no están disponibles en el centro de datos de Nueva Jersey.

2. La respuesta del servidor se enruta hacia la DIRECCIÓN IP asociada a la dirección IP original a través de la única ruta disponible, lo que da como resultado que la respuesta vuelva a lo largo de la misma ruta de red.

![Solución de enrutamiento Asymetric de ExpressRoute 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problema 2: Conexión de nube a local a través de ExpressRoute
  
En el siguiente diagrama se muestra la ruta de acceso de red asimétrica que se toma cuando la configuración de red no proporciona NAT para las solicitudes entrantes de la nube de Microsoft a través de ExpressRoute.
  
1. La solicitud entrante de Office 365 recupera la dirección IP de DNS y envía la solicitud a la red perimetral.

2. En esta configuración defectuosa, no hay nat de origen configurada o disponible en la red perimetral donde se envía el tráfico, lo que da como resultado que la dirección IP de origen real se utilice como destino de devolución.

  - El equipo de la red enruta el tráfico devuelto a Office 365 a través de cualquier conexión de red de ExpressRoute disponible.

  - El resultado es una conexión asimétrica a Office 365.

![Problema de enrutamiento asimétrico de ExpressRoute 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Solución 2: NAT de origen
  
Simplemente agregar un NAT de origen a la solicitud entrante resuelve esta red mal configurada. En este diagrama:
  
1. La solicitud entrante sigue entrando a través de la red perimetral del centro de datos de Nueva York. Esta vez nat de origen está disponible.

2. La respuesta del servidor se enruta de nuevo hacia la DIRECCIÓN IP asociada con nat de origen en lugar de la dirección IP original, lo que da como resultado que la respuesta vuelva a lo largo de la misma ruta de red.

![Solución de enrutamiento Asymetric de ExpressRoute 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Papel para comprobar que el diseño de red tiene simetría de ruta de acceso

En este punto, debe comprobar en papel que el plan de implementación ofrece simetría de ruta para los diferentes escenarios en los que va a usar Office 365. Identificará la ruta de red específica que se espera tomar cuando una persona use características diferentes del servicio. Desde la red local y el enrutamiento WAN, hasta los dispositivos perimetrales, hasta la ruta de conectividad; ExpressRoute o Internet, y en la conexión al punto de conexión en línea.
  
Tendrá que hacerlo para todos los servicios de red Office 365 que se identificaron anteriormente como servicios que adoptará su organización.
  
Ayuda a hacer este recorrido por las rutas con una segunda persona. Explíqueles de dónde se espera que cada salto de red obtenga su siguiente ruta y asegúrese de que está familiarizado con las rutas de enrutamiento. Recuerde que ExpressRoute siempre proporcionará una ruta con más ámbito a las direcciones IP de Microsoft Server, lo que le dará un costo de ruta menor que una ruta predeterminada de Internet.
  
### <a name="design-client-connectivity-configuration"></a>Configuración de conectividad de cliente de diseño
<a name="asymmetric"> </a>

![Uso de archivos PAC con ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Si usa un servidor proxy para el tráfico enlazado a Internet, debe ajustar los archivos de configuración de cliente o PAC para asegurarse de que los equipos cliente de la red estén configurados correctamente para enviar el tráfico de ExpressRoute que desea Office 365 sin transitar el servidor proxy y el tráfico restante, incluido algún tráfico de Office 365, se envía al proxy correspondiente. Lea nuestra guía sobre [cómo administrar Office 365 puntos de conexión como,](./managing-office-365-endpoints.md) por ejemplo, los archivos PAC.
  
> [!NOTE]
> Los puntos de conexión cambian con frecuencia, tan a menudo como semanalmente. Solo debe realizar cambios en función de los servicios y características que su organización ha adoptado para reducir el número de cambios que necesitará realizar para mantenerse al día. Preste especial atención  a la fecha de vigencia en la fuente RSS donde se anuncian los cambios y se mantiene un registro de todos los cambios anteriores, las direcciones IP que se anuncian no se pueden anunciar o quitar del anuncio hasta que se alcance la fecha de vigencia.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Crear los procedimientos de implementación y pruebas
<a name="testing"> </a>

El plan de implementación debe incluir tanto la planeación de pruebas como la reversión. Si la implementación no funciona como se esperaba, el plan debe diseñarse para afectar al menor número de personas antes de detectar problemas. A continuación se deberán tener en cuenta algunos principios de alto nivel que el plan debe tener en cuenta.
  
1. Fase del segmento de red y la incorporación del servicio de usuario para minimizar la interrupción.

2. Plan for testing routes with traceroute and TCP connect from a separate Internet connected host.

3. Preferiblemente, las pruebas de los servicios entrantes y salientes deben realizarse en una red de prueba aislada con un inquilino Office 365 prueba.

      - Como alternativa, las pruebas se pueden realizar en una red de producción si el cliente aún no está usando Office 365 o está en fase piloto.

      - Como alternativa, las pruebas se pueden realizar durante una interrupción de producción que se reserva solo para pruebas y supervisión.

      - Como alternativa, las pruebas se pueden realizar comprobando las rutas de cada servicio en cada nodo de enrutador de capa 3. Esta reserva solo debe usarse si no es posible realizar otras pruebas, ya que la falta de pruebas físicas presenta riesgos.

### <a name="build-your-deployment-procedures"></a>Crear los procedimientos de implementación

Los procedimientos de implementación deben implementarse en pequeños grupos de personas en fases para permitir las pruebas antes de implementarlas en grupos más grandes de personas. Las siguientes son varias maneras de faser la implementación de ExpressRoute.
  
1. Configure ExpressRoute con el emparejamiento de Microsoft y reenvíe los anuncios de ruta a un único host solo con fines de pruebas por fases.

2. Anuncie las rutas a la red de ExpressRoute en un único segmento de red al principio y expanda los anuncios de ruta por segmento o región de red.

3. Si implementa Office 365 por primera vez, use la implementación de red de ExpressRoute como piloto para un número reducido de personas.

4. Si usa servidores proxy, también puede configurar un archivo PAC de prueba para dirigir un pequeño número de personas a ExpressRoute con pruebas y comentarios antes de agregar más.

El plan de implementación debe enumerar cada uno de los procedimientos de implementación que se deben tomar o los comandos que deben usarse para implementar la configuración de red. Cuando llegue el tiempo de interrupción de la red, todos los cambios que se realicen deben ser del plan de implementación escrito que se escribió por adelantado y revisado por el mismo nivel. Consulte nuestras instrucciones sobre la configuración técnica de ExpressRoute.
  
- Actualizar los registros TXT de SPF si ha cambiado las direcciones IP de los servidores locales que seguirán mandando correo electrónico.

- Actualizar las entradas DNS de los servidores locales si ha cambiado las direcciones IP para dar cabida a una nueva configuración nat.

- Asegúrese de que se ha suscrito a la fuente RSS Office 365 notificaciones de extremo para mantener cualquier configuración de enrutamiento o proxy.

Una vez completada la implementación de ExpressRoute, se deben ejecutar los procedimientos del plan de prueba. Se deben registrar los resultados de cada procedimiento. Debe incluir procedimientos para volver al entorno de producción original en caso de que los resultados del plan de prueba indiquen que la implementación no se ha realizado correctamente.
  
### <a name="build-your-test-procedures"></a>Crear los procedimientos de prueba

Los procedimientos de prueba deben incluir pruebas para cada servicio de red entrante y saliente para Office 365 que usarán ExpressRoute y las que no lo harán. Los procedimientos deben incluir pruebas desde cada ubicación de red única, incluidos los usuarios que no están locales en la LAN corporativa.
  
Algunos ejemplos de actividades de prueba son los siguientes.
  
1. Haga ping desde el enrutador local al enrutador del operador de red.

2. Valide los más de 500 Office 365 y los anuncios de direcciones IP de CRM Online los recibe el enrutador local.

3. Valide que el NAT entrante y saliente funciona entre ExpressRoute y la red interna.

4. Valide que las rutas a nat se anuncian desde el enrutador.

5. Valide que ExpressRoute ha aceptado los prefijos anunciados.

      - Use el siguiente cmdlet para comprobar los anuncios de emparejamiento:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Validar que el intervalo IP NAT público no se anuncia a Microsoft a través de ningún otro circuito de red pública de ExpressRoute o de Internet, a menos que sea un subconjunto específico de un intervalo mayor como en el ejemplo anterior.

7. Los circuitos de ExpressRoute están emparejados, validan que se estén ejecutando ambas sesiones de BGP.

8. Configure un único host en el interior de su NAT y use ping, tracert y tcpping para probar la conectividad a través del nuevo circuito al host outlook.office365.com. Como alternativa, puede usar una herramienta como Wireshark o Microsoft Network Monitor 3.4 en un puerto reflejado al MSEE para validar que puede conectarse a la dirección IP asociada con outlook.office365.com.

9. Probar la funcionalidad de nivel de aplicación Exchange Online.

  - Test Outlook es capaz de conectarse a Exchange Online y enviar y recibir correo electrónico.

  - La Outlook puede usar el modo en línea.

  - Probar la conectividad de smartphones y la funcionalidad de envío y recepción.

10. Probar la funcionalidad de nivel de aplicación para SharePoint Online

  - Pruebe OneDrive para la Empresa de sincronización.

  - Probar SharePoint web en línea.

11. Probar la funcionalidad de nivel de aplicación Skype Empresarial escenarios de llamadas:

  - Unirse a una llamada de conferencia como usuario autenticado [invitación iniciada por el usuario final].

  - Invitar al usuario a una llamada de conferencia [invitación enviada desde MCU].

  - Únase a la conferencia como usuario anónimo mediante la Skype Empresarial web.

  - Unirse a la llamada desde la conexión de pc cableada, el teléfono IP y el dispositivo móvil.

  - Llamada al usuario federado o Llamada a validación RTC: la llamada se ha completado, la calidad de la llamada es aceptable, el tiempo de conexión es aceptable.

  - Compruebe que el estado de presencia de los contactos se actualiza tanto para los miembros del inquilino como para los usuarios federados.

### <a name="common-problems"></a>Problemas comunes

El enrutamiento asimétrico es el problema de implementación más común. Estos son algunos orígenes comunes para buscar:
  
- Usar una topología de enrutamiento de red abierta o plana sin NAT de origen en su lugar.

- No usar SNAT para enrutar a los servicios entrantes a través de las conexiones de Internet y ExpressRoute.

- No probar los servicios entrantes en ExpressRoute en una red de prueba antes de implementarse de forma general.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Implementar la conectividad de ExpressRoute a través de la red
<a name="testing"> </a>

Escenifique la implementación en un segmento de la red a la vez, implementando progresivamente la conectividad a diferentes partes de la red con un plan para revertir cada nuevo segmento de red. Si la implementación está alineada con una implementación Office 365, implemente en su Office 365 usuarios piloto primero y extienda desde allí.
  
Primero para la prueba y luego para la producción:
  
- Ejecute los pasos de implementación para habilitar ExpressRoute.

- Pruebe que las rutas de red son las esperadas.

- Realice pruebas en cada servicio entrante y saliente.

- Reversión si detecta algún problema.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Configurar una conexión de prueba a ExpressRoute con un segmento de red de prueba

Ahora que tiene el plan completado en papel, es el momento de probar a pequeña escala. En esta prueba, establecerá una única conexión de ExpressRoute con Microsoft Peering a una subred de prueba en la red local. Puede configurar un inquilino de [prueba Office 365](https://go.microsoft.com/fwlink/p/?LinkID=403802) con conectividad a y desde la subred de prueba e incluir todos los servicios salientes y entrantes que va a usar en producción en la subred de prueba. Configure DNS para el segmento de red de prueba y establezca todos los servicios entrantes y salientes. Ejecute el plan de prueba y asegúrese de que está familiarizado con el enrutamiento de cada servicio y la propagación de rutas.
  
### <a name="execute-the-deployment-and-test-plans"></a>Ejecutar los planes de implementación y prueba

Al completar los elementos descritos anteriormente, descátese de las áreas que ha completado y asegúrese de que usted y su equipo los han revisado antes de ejecutar los planes de implementación y pruebas.
  
- Lista de servicios salientes y entrantes que participan en el cambio de red.

- Diagrama de arquitectura de red global que muestra las ubicaciones de salida de Internet y ExpressRoute.

- Diagrama de enrutamiento de red que muestra las distintas rutas de red usadas para cada servicio implementado.

- Un plan de implementación con pasos para implementar los cambios y la reversión si es necesario.

- Un plan de prueba para probar cada Office 365 y servicio de red.

- Validación en papel completada de las rutas de producción para los servicios entrantes y salientes.

- Una prueba completada en un segmento de red de prueba, incluidas las pruebas de disponibilidad.

Elija una ventana de interrupción que sea lo suficientemente larga como para ejecutar todo el plan de implementación y el plan de prueba, tiene tiempo disponible para solucionar problemas y tiempo para revertir si es necesario.
  
> [!CAUTION]
> Debido a la naturaleza compleja del enrutamiento a través de Internet y ExpressRoute, se recomienda agregar tiempo de búfer adicional a esta ventana para solucionar problemas de enrutamiento complejo.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Configurar QoS para Skype Empresarial Online

QoS es necesario para obtener ventajas de voz y reunión para Skype Empresarial Online. Puede configurar QoS después de asegurarse de que la conexión de red de ExpressRoute no bloquee ninguno de los demás accesos Office 365 servicio. La configuración de QoS se describe en el artículo [ExpressRoute y QoS en Skype Empresarial Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .
  
## <a name="troubleshooting-your-implementation"></a>Solución de problemas de la implementación
<a name="troubleshooting"> </a>

El primer lugar para ver es en los pasos de esta guía de implementación, ¿se ha perdido alguna falta en el plan de implementación? Vuelva atrás y ejecute más pruebas de red pequeñas si es posible para replicar el error y depurarlo allí.
  
Identificar qué servicios entrantes o salientes fallaron durante las pruebas. Obtenga específicamente las direcciones IP y subredes de cada uno de los servicios que han fallado. Sigue adelante y sigue el diagrama de topología de red en papel y valida el enrutamiento. Valide específicamente dónde se anuncia el enrutamiento de ExpressRoute, pruebe ese enrutamiento durante la interrupción si es posible con seguimientos.
  
Ejecute PSPing con un seguimiento de red a cada extremo de cliente y evalúe las direcciones IP de origen y de destino para validar que son las esperadas. Ejecute telnet en cualquier host de correo que exponga en el puerto 25 y compruebe que SNAT oculta la dirección IP de origen original si se espera.
  
Tenga en cuenta que al implementar Office 365 con una conexión de ExpressRoute, deberá asegurarse de que la configuración de red de ExpressRoute está diseñada de forma óptima y también ha optimizado los demás componentes de la red, como los equipos cliente. Además de usar esta guía de planeación para solucionar los pasos que puede haber perdido, también hemos escrito un plan de solución de problemas de [rendimiento para Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/implementexpressroute365]()
  
## <a name="related-topics"></a>Temas relacionados

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Uso de comunidades BGP en ExpressRoute para Office 365 escenarios](bgp-communities-in-expressroute.md)
  
[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimización de la red para Skype Empresarial Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute y calidad del servicio en Skype Empresarial Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flujo de llamadas con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Intervalos de direcciones IP y URL de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)