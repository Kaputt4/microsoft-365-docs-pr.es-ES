---
title: Uso de comunidades DE BGP en ExpressRoute para escenarios de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Obtenga información sobre cómo usar las comunidades DE BGP en Azure ExpressRoute para administrar el número de prefijos IP y el ancho de banda necesario para escenarios de Office 365.
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694073"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Uso de comunidades DE BGP en ExpressRoute para escenarios de Office 365

La conexión a Office 365 con Azure ExpressRoute se basa en anuncios BGP de subredes IP específicas que representan redes donde se implementan puntos de conexión de Office 365. Debido a la naturaleza global de Office 365 y al número de servicios que constituyen Office 365, los clientes a menudo tienen que administrar los anuncios que aceptan en su red. Reducir el número de subredes IP; A lo largo del resto de este artículo, para alinearse con la terminología de administración de red BGP, se cumplen los siguientes objetivos finales para los clientes:
  
- Administrar el número de prefijos **IP** anunciados aceptados: los clientes que tienen una infraestructura de red interna o operador de red que solo admite un número limitado de prefijos IP y los clientes que tienen un operador de red que cobra por aceptar prefijos superiores a un número limitado querrán evaluar el número total de prefijos ya anunciados a su red y seleccionar qué aplicaciones de Office 365 son más adecuadas para ExpressRoute.

- Administrar la cantidad de ancho de banda necesaria en el circuito de **Azure ExpressRoute:** es posible que los clientes quieran controlar el sobre de ancho de banda de los servicios de Office 365 a través de la ruta de acceso de ExpressRoute frente a la ruta de Internet. Esto permite a los clientes reservar el ancho de banda de ExpressRoute para aplicaciones específicas como Skype Empresarial y enrutar las aplicaciones de Office 365 restantes a través de la ruta de Internet.

Para ayudar a los clientes con estos objetivos, los prefijos IP de Office 365 que se anuncian a través de ExpressRoute se etiquetan con valores específicos de la comunidad BGP del servicio, como se muestra en el ejemplo siguiente.
  
> [!NOTE]
> Debes esperar que parte del tráfico de red asociado con otras aplicaciones se incluya en el valor de la comunidad. Este es el comportamiento esperado para una oferta global de software como servicio con centros de datos y servicios compartidos. Esto se ha minimizado siempre que sea posible con los dos objetivos anteriores, administrando el recuento de prefijos o el ancho de banda en mente.

|**Servicio**|**Valor de la comunidad BGP**|**Notas**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Incluye servicios de Exchange y EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype Empresarial\*  <br/> |12076:5030  <br/> |Skype Empresarial Online & servicios de Microsoft Teams  <br/> |
|Otros servicios de Office 365\*  <br/> |12076:5100  <br/> |Incluye Azure Active Directory (escenarios de autenticación y sincronización de directorios), así como servicios del portal de Office 365  <br/> |
|\*El ámbito de los escenarios de servicio incluidos en ExpressRoute se documenta en el artículo de puntos de conexión [de Office 365.](https://aka.ms/o365endpoints)  <br/> \*\*Es posible que en el futuro se puedan agregar servicios adicionales y valores de la comunidad BGP. [Consulta la lista actual de comunidades BGP.](https://azure.microsoft.com/documentation/articles/expressroute-routing/)  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>¿Cuáles son los escenarios más comunes para usar comunidades BGP?

Los clientes pueden usar comunidades BGP para regular grupos de prefijos IP aceptados por su red a través de Azure ExpressRoute, lo que influye en el recuento total de prefijos IP y el sobre de ancho de banda esperado de determinados servicios de Office 365. Es importante comprender que todo Office 365 requerirá tráfico enlazado a Internet independientemente del uso de Azure ExpressRoute o las comunidades BGP. Los tres escenarios siguientes son los usos más comunes de esta funcionalidad.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Escenario 1: Minimizar el número de prefijos IP de Office 365

Contoso Corporation es una empresa de 50 000 personas que actualmente usa Office 365 para Exchange Online y SharePoint Online. Al revisar los requisitos de ExpressRoute, Contoso determina que sus dispositivos de red en muchas ubicaciones regionales no pueden controlar tamaños de tabla de enrutamiento superiores a 100 entradas de ruta adicionales. Contoso revisó el número total de prefijos IP que ExpressRoute anunciaría para el conjunto completo de servicios de Office 365 y llegó a la conclusión de que supera los 100. Para permanecer por debajo de las 100 entradas de ruta adicionales, Contoso incluye el uso de ExpressRoute para Office 365 solo al valor de la comunidad BGP de SharePoint Online, 12076:5020, recibido a través del emparejamiento de Microsoft de ExpressRoute.

|**Etiqueta de comunidad DE BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |OneDrive para la Empresa de SharePoint Online &amp;  <br/> | Solicitudes DNS, CRL y &amp; CDN  <br/>  Todos los demás servicios de Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/>  Portal de Office 365, autenticación de Office 365, &amp; Office en un explorador  <br/>  Exchange Online, Exchange Online Protection y Skype Empresarial Online  <br/> |

> [!NOTE]
> Para lograr recuentos de prefijos inferiores para cada servicio, persistirá una cantidad mínima de superposición entre servicios. Este es el comportamiento esperado.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Escenario 2: Ámbito de ExpressRoute y uso de ancho de banda interno para algunos servicios de Office 365

Fabrikam Inc, una gran empresa nacional con una red heterogéneo distribuida, es suscriptor de muchos servicios de Office 365, incluidos; Exchange Online, SharePoint Online y Skype Empresarial Online. La infraestructura de enrutamiento interno de Fabrikam puede controlar miles de prefijos IP en sus tablas de enrutamiento; Sin embargo, Fabrikam solo desea aprovisionar ExpressRoute y el ancho de banda interno para las aplicaciones de Office 365 que son más sensibles al rendimiento de la red y usar su ancho de banda de Internet existente para todas las demás aplicaciones de Office 365.
  
Por este motivo, Fabrikam enruta su ancho de banda de Azure ExpressRoute solo al valor de la comunidad BGP de Skype Empresarial Online, 12076:5030, recibido a través del emparejamiento de Microsoft de ExpressRoute. El tráfico de red restante asociado a Office 365 sigue utilizando los puntos de salida de Internet.

|**Etiqueta de comunidad DE BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> (12076:5030)  <br/> |Señalización SIP de Skype, descargas, voz, vídeo y uso compartido de escritorio  <br/> | Solicitudes DNS, CRL y &amp; CDN  <br/>  Todos los demás servicios de Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/>  Portal de Office 365, autenticación de Office 365, &amp; Office en un explorador  <br/>  Telemetría de Skype Empresarial, sugerencias rápidas de cliente de Skype, conectividad de mensajería instantánea pública  <br/>  Exchange Online, Exchange Online Protection y SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Escenario 3: Ámbito de Azure ExpressRoute solo para servicios de Office 365

Woodgrove Bank es un cliente de varios servicios en la nube de Microsoft, incluido Office 365. Después de evaluar su capacidad y consumo de red, Woodgrove Bank decide implementar Azure ExpressRoute como la ruta preferida para los servicios de Office 365 compatibles. Las tablas de enrutamiento pueden admitir el conjunto completo de prefijos IP de Office 365 y los circuitos de Azure ExpressRoute que han aprovisionado admiten todas las necesidades de latencia y ancho de banda proyectados.
  
Para garantizar el tráfico de red asociado con servicios en la nube de Microsoft distintos de Office 365, Woodgrove Bank asigna el uso de ExpressRoute para Office 365 a todos los prefijos IP etiquetados con valores específicos de la comunidad BGP de Office 365, 12076:5010, 12076:5020, 12076:5100.

|**Etiqueta de comunidad DE BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|Exchange, Skype Empresarial & Microsoft Teams, SharePoint y &amp; otros servicios  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> OneDrive para la Empresa de SharePoint Online &amp;  <br/> Señalización SIP de Skype, descargas, voz, vídeo y uso compartido de escritorio  <br/> Portal de Office 365, autenticación de Office 365, &amp; Office en un explorador  <br/> | Solicitudes DNS, CRL y &amp; CDN  <br/>  Todos los demás servicios de Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Consideraciones clave de planeación para usar comunidades BGP

Los clientes que eligen aprovechar las comunidades DE BGP para influir en la forma en que ExpressRoute se anuncia y propaga a través de la red del cliente deben tener en cuenta las siguientes consideraciones:
  
- Al usar comunidades BGP en el diseño de red, es importante asegurarse de que la simetría de rutas se mantiene. En algunos casos, la adición o eliminación de comunidades BGP puede crear una situación en la que se rompe el enrutamiento simétrico y se debe actualizar la configuración de enrutamiento para restablecer el enrutamiento simétrico.

- El ámbito de Azure ExpressRoute con los valores de la comunidad BGP es una acción del cliente. Microsoft anunciará todos los prefijos IP asociados a la relación de emparejamiento, independientemente de los ámbitos configurados por el cliente.

- Azure ExpressRoute no admite ninguna acción en la red de Microsoft en función de las comunidades BGP asignadas por el cliente.

- Los prefijos IP usados por Office 365 solo se marcan con valores específicos de la comunidad BGP del servicio, no se admiten comunidades BGP específicas de ubicación. Los servicios de Office 365 son de carácter global, por lo que no se admiten prefijos de filtrado basados en la ubicación del espacio empresarial o los datos dentro de la nube de Office 365. El enfoque recomendado es configurar la red para coordinar la ruta de red más corta o preferida desde la ubicación de red del usuario a la red global de Microsoft, independientemente de la ubicación física de la dirección IP del servicio de Office 365 que solicite.

- Los prefijos IP incluidos en cada valor de la comunidad BGP representan una subred que contiene direcciones IP para la aplicación de Office 365 asociada con el valor. En algunos casos, más de una aplicación de Office 365 tiene direcciones IP dentro de una subred, lo que da como resultado un prefijo IP existente en más de un valor de la comunidad. Este comportamiento se espera, aunque rara vez, debido a la fragmentación de la asignación y no afecta al recuento de prefijos ni a los objetivos de administración de ancho de banda. Se recomienda a los clientes usar el enfoque "permitir lo que se necesita" en lugar de "denegar lo que no es necesario" al aprovechar las comunidades DE BGP para Office 365 para minimizar el efecto.

- El uso de comunidades BGP no cambia los requisitos de conectividad de red subyacentes ni la configuración necesaria para usar Office 365. Los clientes que quieran acceder a Office 365 aún deben poder acceder a Internet.

- El ámbito de Azure ExpressRoute con las comunidades BGP solo afecta a las rutas que la red interna puede ver a través de la relación de emparejamiento de Microsoft. Es posible que deba realizar configuraciones de nivel de aplicación adicionales, como el uso de una configuración PAC o WPAD junto con el enrutamiento con ámbito.

- Además de usar las comunidades BGP asignadas por Microsoft, los clientes pueden elegir asignar sus propias comunidades BGP a prefijos IP de Office 365 aprendidos a través de Azure ExpressRoute para influir en el enrutamiento interno. Un caso de uso popular es asignar una comunidad BGP basada en ubicación a todas las rutas aprendidas a través de cada ubicación de emparejamiento de ExpressRoute determinada y, a continuación, usar esa información en la red del cliente para coordinar la ruta de red más corta o preferida en la red de Microsoft. El uso de comunidades BGP asignadas por el cliente con ExpressRoute para escenarios de Office 365 está fuera del ámbito de control o visibilidad de Microsoft.

Este es un vínculo breve que puede usar para volver: [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) .
  
## <a name="related-topics"></a>Temas relacionados

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute y calidad del servicio en Skype Empresarial Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flujo de llamadas con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)
  
[Compatibilidad con comunidades BGP](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Aprendizaje de Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer)
