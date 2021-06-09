---
title: Uso de comunidades BGP en ExpressRoute para Office 365 escenarios
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
description: Obtenga información sobre cómo usar las comunidades BGP en Azure ExpressRoute para administrar el número de prefijos IP y el ancho de banda necesario para Office 365 escenarios.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905217"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Uso de comunidades BGP en ExpressRoute para Office 365 escenarios

La conexión a Office 365 con Azure ExpressRoute se basa en anuncios BGP de subredes IP específicas que representan redes donde Office 365 se implementan los puntos de conexión. Debido a la naturaleza global de Office 365 y al número de servicios que constituyen Office 365, los clientes suelen tener la necesidad de administrar los anuncios que aceptan en su red. Reducir el número de subredes IP; Denominados prefijos IP a lo largo del resto de este artículo, para alinearse con la terminología de administración de red BGP, sirve a los siguientes objetivos finales para los clientes:
  
- Administrar el número de prefijos **IP** anunciados aceptados: los clientes que tienen una infraestructura de red interna o un operador de red que solo admite un número limitado de prefijos IP y clientes que tienen un operador de red que cobra por aceptar prefijos por encima de un número limitado, querrán evaluar el número total de prefijos ya anunciados en su red y seleccionar qué aplicaciones Office 365 son las más adecuadas para ExpressRoute.

- Administrar la cantidad de ancho de banda necesaria en el circuito **de Azure ExpressRoute:** es posible que los clientes quieran controlar el sobre de ancho de banda de los servicios Office 365 sobre la ruta de acceso de ExpressRoute frente a internet. Esto permite a los clientes reservar el ancho de banda de ExpressRoute para aplicaciones específicas, como Skype Empresarial y enrutar el resto de Office 365 a través de la ruta de Acceso a Internet.

Para ayudar a los clientes con estos objetivos, Office 365 prefijos IP que se anuncian a través de ExpressRoute se etiquetan con valores de comunidad BGP específicos del servicio, como se muestra en el ejemplo siguiente.
  
> [!NOTE]
> Debe esperar que se incluya algo de tráfico de red asociado con otras aplicaciones en el valor de la comunidad. Este es el comportamiento esperado para una oferta global de software como servicio con centros de datos y servicios compartidos. Esto se ha minimizado siempre que sea posible con los dos objetivos anteriores, ya que se tiene en cuenta la administración del recuento de prefijos o el ancho de banda.

|**Servicio**|**Valor Community BGP**|**Notas**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Incluye servicios Exchange e EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype Empresarial\*  <br/> |12076:5030  <br/> |Skype Empresarial Servicios & Microsoft Teams en línea  <br/> |
|Otros Office 365 servicios\*  <br/> |12076:5100  <br/> |Incluye Azure Active Directory (escenarios de autenticación y sincronización de directorios) así como servicios Office 365 Portal  <br/> |
|\*El ámbito de los escenarios de servicio incluidos en ExpressRoute se documenta en el [Office 365 puntos de conexión.](./urls-and-ip-address-ranges.md)  <br/> \*\*Los servicios adicionales y los valores de la comunidad BGP pueden agregarse en el futuro. [Vea la lista actual de comunidades BGP](/azure/expressroute/expressroute-routing).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>¿Cuáles son los escenarios más comunes para usar comunidades BGP?

Los clientes pueden usar comunidades BGP para regular grupos de prefijos IP aceptados por su red a través de Azure ExpressRoute, lo que influye en el recuento total de prefijos IP y el ancho de banda esperado de determinados servicios Office 365 ip. Es importante comprender que todas las Office 365 requerirán tráfico enlazado a Internet independientemente del uso de Azure ExpressRoute o comunidades BGP. Los tres escenarios siguientes son los usos más comunes de esta funcionalidad.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Escenario 1: Minimizar el número de Office 365 prefijos IP

Contoso Corporation es una compañía de 50 000 personas que actualmente usa Office 365 para Exchange Online y SharePoint Online. Al revisar los requisitos de ExpressRoute Contoso determina que sus dispositivos de red en muchas ubicaciones regionales no pueden controlar tamaños de tabla de enrutamiento superiores a 100 entradas de ruta adicionales. Contoso revisó el número total de prefijos IP que ExpressRoute anunciaría para el conjunto completo de servicios Office 365 y llegó a la conclusión de que supera los 100. Para mantenerse bajo las 100 entradas de ruta adicionales, Contoso usa ExpressRoute para Office 365 solo al valor de la comunidad BGP en línea de SharePoint, 12076:5020, recibido a través del emparejamiento de Microsoft de ExpressRoute.

|**Etiqueta de comunidad BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint En &amp; línea OneDrive para la Empresa  <br/> | DNS, CRL, &amp; CDN solicitudes  <br/>  Todos los demás Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/>  Office 365 portal, Office 365 autenticación, &amp; Office en un explorador  <br/>  Exchange Online, Exchange Online Protection y Skype Empresarial Online  <br/> |

> [!NOTE]
> Para lograr recuentos de prefijos inferiores para cada servicio, persistirá una cantidad mínima de superposición entre servicios. Este es el comportamiento esperado.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Escenario 2: Ámbito de ExpressRoute y uso de ancho de banda interno en algunos Office 365 servicios

Fabrikam Inc, una gran empresa multinacionales con una red heterogéneo distribuida, es un suscriptor de muchos Office 365 servicios, incluidos; Exchange Online, SharePoint Online y Skype Empresarial Online. La infraestructura de enrutamiento interno de Fabrikam puede controlar miles de prefijos IP en sus tablas de enrutamiento; Sin embargo, Fabrikam solo quiere aprovisionar ExpressRoute y el ancho de banda interno para las aplicaciones Office 365 que son las más sensibles al rendimiento de la red y usar su ancho de banda de Internet existente para todas las demás aplicaciones Office 365 web.
  
Por este motivo, Fabrikam usa el ámbito de su ancho de banda de Azure ExpressRoute Skype Empresarial solo un valor Community BGP en línea, 12076:5030, recibido a través del emparejamiento de Microsoft de ExpressRoute. El tráfico de red restante asociado Office 365 sigue utilizando los puntos de salida de Internet.

|**Etiqueta de comunidad BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> (12076:5030)  <br/> |Skype Señalización SIP, descargas, voz, vídeo y uso compartido de escritorio  <br/> | DNS, CRL, &amp; CDN solicitudes  <br/>  Todos los demás Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/>  Office 365 portal, Office 365 autenticación, &amp; Office en un explorador  <br/>  Skype Empresarial telemetría, Skype sugerencias rápidas de cliente, conectividad de mensajería instantánea pública  <br/>  Exchange Online, Exchange Online Protection y SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Escenario 3: Ámbito de Azure ExpressRoute solo Office 365 servicios

Woodgrove Bank es un cliente de varios servicios en la nube de Microsoft, incluidos Office 365. Después de evaluar su capacidad y consumo de red, Woodgrove Bank decide implementar Azure ExpressRoute como la ruta preferida para los servicios Office 365 compatibles. Las tablas de enrutamiento pueden admitir el conjunto completo de prefijos IP Office 365 y los circuitos de Azure ExpressRoute que han aprovisionado admiten todas las necesidades de ancho de banda y latencia proyectados.
  
Para garantizar el tráfico de red asociado Office 365 los servicios en la nube de Microsoft distintos de Office 365, Woodgrove Bank hace un ámbito del uso de ExpressRoute para Office 365 todos los prefijos IP etiquetados con valores específicos de la comunidad BGP, 12076:5010, 12076:5020, 12076:5100.

|**Etiqueta de comunidad BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|Exchange, Skype Empresarial & Microsoft Teams, SharePoint, &amp; otros servicios  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp;Exchange Online Exchange Online Protection  <br/> SharePoint En &amp; línea OneDrive para la Empresa  <br/> Skype Señalización SIP, descargas, voz, vídeo y uso compartido de escritorio  <br/> Office 365 portal, Office 365 autenticación, &amp; Office en un explorador  <br/> | DNS, CRL, &amp; CDN solicitudes  <br/>  Todos los demás Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Consideraciones clave de planeación para usar comunidades BGP

Los clientes que decidan aprovechar las comunidades BGP para influir en la forma en que Se anuncia y propaga ExpressRoute a través de la red de clientes deben tener en cuenta las siguientes consideraciones:
  
- Cuando se usan comunidades BGP en el diseño de red, es importante asegurarse de que la simetría de rutas se mantenga. En algunos casos, la adición o eliminación de comunidades BGP puede crear una situación en la que el enrutamiento simétrico se rompe y la configuración de enrutamiento debe actualizarse para restablecer el enrutamiento simétrico.

- El ámbito de Azure ExpressRoute con valores de la comunidad BGP es una acción del cliente. Microsoft anunciará todos los prefijos IP asociados con la relación de emparejamiento independientemente de los ámbitos configurados por el cliente.

- Azure ExpressRoute no admite ninguna acción en la red de Microsoft en función de las comunidades BGP asignadas por el cliente.

- Los prefijos IP usados por Office 365 solo se marcan con valores de comunidad BGP específicos del servicio, no se admiten comunidades BGP específicas de ubicación. Office 365 los servicios son de naturaleza global, no se admiten prefijos de filtrado basados en la ubicación del espacio empresarial o los datos dentro de la nube Office 365 usuario. El enfoque recomendado es configurar la red para coordinar la ruta de acceso de red más corta o preferida desde la ubicación de red del usuario a la red global de Microsoft, independientemente de la ubicación física de la dirección IP del servicio Office 365 que están solicitando.

- Los prefijos IP incluidos en cada valor de la comunidad BGP representan una subred que contiene direcciones IP para la aplicación Office 365 asociada al valor. En algunos casos, más de Office 365 aplicación tiene direcciones IP dentro de una subred, lo que da como resultado un prefijo IP existente en más de un valor de comunidad. Este comportamiento se espera, aunque rara vez, debido a la fragmentación de asignación y no afecta al recuento de prefijos ni a los objetivos de administración de ancho de banda. Se anima a los clientes a usar el enfoque "permitir lo que se necesita" en lugar de "denegar lo que no es necesario" al aprovechar las comunidades BGP para Office 365 para minimizar el efecto.

- El uso de comunidades BGP no cambia los requisitos o la configuración de conectividad de red subyacentes necesarios para usar Office 365. Los clientes que quieran acceder a Office 365 deben tener acceso a Internet.

- El ámbito de Azure ExpressRoute con comunidades BGP solo afecta a las rutas que la red interna puede ver a través de la relación de emparejamiento de Microsoft. Es posible que deba realizar configuraciones de nivel de aplicación adicionales, como el uso de una configuración pac o WPAD junto con el enrutamiento con ámbito.

- Además de usar las comunidades BGP asignadas por Microsoft, los clientes pueden elegir asignar sus propias comunidades BGP Office 365 prefijos IP aprendidos a través de Azure ExpressRoute para influir en el enrutamiento interno. Un caso de uso popular es asignar una comunidad BGP basada en ubicación a todas las rutas aprendidas a través de cada ubicación de emparejamiento de ExpressRoute determinada y, a continuación, usar esa información en la red del cliente para coordinar la ruta de acceso de red más corta o preferida en la red de Microsoft. El uso de comunidades BGP asignadas por el cliente con ExpressRoute para escenarios Office 365 está fuera del ámbito del control o visibilidad de Microsoft.

Este es un breve vínculo que puede usar para volver: [https://aka.ms/bgpexpressroute365]() .
  
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
  
[Compatibilidad con comunidades BGP](/azure/expressroute/expressroute-routing)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Aprendizaje de Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer)