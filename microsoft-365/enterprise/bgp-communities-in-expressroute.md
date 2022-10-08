---
title: Uso de comunidades BGP en ExpressRoute para escenarios de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
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
description: Aprenda a usar comunidades BGP en Azure ExpressRoute para administrar el número de prefijos IP y el ancho de banda necesario para Office 365 escenarios.
ms.openlocfilehash: 44ec80f67d1ce3e006e5359c0b6480543a09b791
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68163500"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Uso de comunidades BGP en ExpressRoute para escenarios de Office 365

La conexión a Office 365 mediante Azure ExpressRoute se basa en anuncios BGP de subredes IP específicas que representan redes donde se implementan Office 365 puntos de conexión. Debido a la naturaleza global de Office 365 y al número de servicios que constituyen Office 365, los clientes a menudo tienen la necesidad de administrar los anuncios que aceptan en su red. Reducir el número de subredes IP; Denominados prefijos IP durante el resto de este artículo, para alinearse con la terminología de administración de redes BGP, cumple los siguientes objetivos finales para los clientes:
  
- **Administrar el número de prefijos IP anunciados aceptados**: los clientes que tengan una infraestructura de red interna o un operador de red que solo admitan un número limitado de prefijos IP y los clientes que tengan un operador de red que cobra por aceptar prefijos por encima de un número limitado querrán evaluar el número total de prefijos que ya se anuncian en su red y seleccionar qué aplicaciones Office 365 son más adecuadas para ExpressRoute.

- **Administrar la cantidad de ancho de banda necesario en el circuito ExpressRoute de Azure**: es posible que los clientes quieran controlar el sobre de ancho de banda de los servicios de Office 365 a través de la ruta de acceso de ExpressRoute frente a la ruta de acceso a Internet. Esto permite a los clientes reservar el ancho de banda de ExpressRoute para aplicaciones específicas, como Skype Empresarial y enrutar las aplicaciones restantes Office 365 a través de la ruta de acceso a Internet.

Para ayudar a los clientes con estos objetivos, Office 365 prefijos IP que se anuncian a través de ExpressRoute se etiquetan con valores de comunidad BGP específicos del servicio, como se muestra en el ejemplo siguiente.
  
> [!NOTE]
> Debe esperar que algún tráfico de red asociado a otras aplicaciones se incluya en el valor de la comunidad. Este es el comportamiento esperado de una oferta global de software como servicio con servicios compartidos y centros de datos. Esto se ha minimizado siempre que sea posible teniendo en cuenta los dos objetivos anteriores, la administración del recuento de prefijos o el ancho de banda.

|**Servicio**|**Valor de la comunidad BGP**|**Notas**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Incluye servicios de Exchange y EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype Empresarial\*  <br/> |12076:5030  <br/> |Skype Empresarial servicios de Microsoft Teams & en línea  <br/> |
|Otros servicios de Office 365\*  <br/> |12076:5100  <br/> |Incluye Azure Active Directory (escenarios de autenticación y sincronización de directorios), así como servicios de Office 365 Portal  <br/> |
|\*El ámbito de los escenarios de servicio incluidos en ExpressRoute se documenta en el artículo [Office 365 puntos de conexión](./urls-and-ip-address-ranges.md).  <br/> \*\*En el futuro se pueden agregar servicios adicionales y valores de comunidad bgp. [Consulte la lista actual de comunidades BGP](/azure/expressroute/expressroute-routing).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>¿Cuáles son los escenarios más comunes para usar comunidades BGP?

Los clientes pueden usar comunidades bgp para regular grupos de prefijos IP aceptados por su red a través de Azure ExpressRoute, lo que influye en el número total de prefijos IP y en el ancho de banda esperado de determinados servicios de Office 365. Es importante comprender que todos los Office 365 requerirán tráfico enlazado a Internet independientemente del uso de Azure ExpressRoute o de las comunidades BGP. Los tres escenarios siguientes son los usos más comunes de esta funcionalidad.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Escenario 1: Minimizar el número de prefijos IP de Office 365

Contoso Corporation es una empresa de 50 000 personas que actualmente usa Office 365 para Exchange Online y SharePoint Online. Al revisar los requisitos de ExpressRoute, Contoso determina que sus dispositivos de red en muchas ubicaciones regionales no pueden controlar tamaños de tabla de enrutamiento superiores a 100 entradas de ruta adicionales. Contoso ha revisado el número total de prefijos IP que ExpressRoute anunciaría para el conjunto completo de servicios de Office 365 y ha llegado a la conclusión de que supera los 100. Para mantenerse en las 100 entradas de ruta adicionales, Contoso limita el uso de ExpressRoute para Office 365 solo al valor de la comunidad BGP de SharePoint Online, 12076:5020, recibido a través del emparejamiento de Microsoft de ExpressRoute.

|**Etiqueta de comunidad BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive para la Empresa  <br/> | Solicitudes DNS, CRL y &amp; CDN  <br/>  Todos los demás servicios de Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/>  Office 365 portal, autenticación Office 365, &amp; Office en un explorador  <br/>  Exchange Online, Exchange Online Protection y Skype Empresarial Online  <br/> |

> [!NOTE]
> Para lograr recuentos de prefijos inferiores para cada servicio, se conservará una cantidad mínima de superposición entre los servicios. Este es el comportamiento esperado.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Escenario 2: Ámbito de ExpressRoute y uso de ancho de banda interno para algunos servicios de Office 365

Fabrikam Inc, una gran empresa multinacional con una red heterogénea distribuida, es suscriptor de muchos Office 365 servicios, incluidos; Exchange Online, SharePoint Online y Skype Empresarial Online. La infraestructura de enrutamiento interno de Fabrikam puede controlar miles de prefijos IP en sus tablas de enrutamiento; Sin embargo, Fabrikam solo quiere aprovisionar ExpressRoute y ancho de banda interno para las aplicaciones Office 365 que son las más sensibles al rendimiento de la red y usan su ancho de banda de Internet existente para todas las demás aplicaciones Office 365.
  
Por ese motivo, Fabrikam limita su ancho de banda de Azure ExpressRoute a solo Skype Empresarial valor de la comunidad BGP en línea, 12076:5030, recibido a través del emparejamiento de Microsoft de ExpressRoute. El tráfico de red restante asociado a Office 365 sigue usando los puntos de salida de Internet.

|**Etiqueta de comunidad BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> (12076:5030)  <br/> |Señalización sip de Skype, descargas, voz, vídeo y uso compartido de escritorio  <br/> | Solicitudes DNS, CRL y &amp; CDN  <br/>  Todos los demás servicios de Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/>  Office 365 portal, autenticación Office 365, &amp; Office en un explorador  <br/>  Skype Empresarial telemetría, sugerencias rápidas de cliente de Skype, conectividad de mensajería instantánea pública  <br/>  Exchange Online, Exchange Online Protection y SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Escenario 3: Ámbito de Azure ExpressRoute solo para servicios de Office 365

Woodgrove Bank es un cliente de varios servicios en la nube de Microsoft, incluidos Office 365. Después de evaluar su capacidad de red y consumo, Woodgrove Bank decide implementar Azure ExpressRoute como la ruta de acceso preferida para los servicios de Office 365 admitidos. Las tablas de enrutamiento pueden admitir el conjunto completo de prefijos IP de Office 365 y los circuitos de Azure ExpressRoute que han aprovisionado admiten todas las necesidades de ancho de banda y latencia proyectadas.
  
Para garantizar el tráfico de red asociado a servicios en la nube de Microsoft distintos de Office 365, Woodgrove Bank limita el uso de ExpressRoute para Office 365 a todos los prefijos IP etiquetados con Office 365 valores de comunidad BGP específicos, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Etiqueta de comunidad BGP usada**|**Funcionalidad enrutable a través de Azure ExpressRoute**|**Rutas de Internet necesarias**|
|:-----|:-----|:-----|
|Exchange, Skype Empresarial & Microsoft Teams, SharePoint y &amp; otros servicios  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp; Exchange Online Exchange Online Protection  <br/> SharePoint Online &amp; OneDrive para la Empresa  <br/> Señalización sip de Skype, descargas, voz, vídeo y uso compartido de escritorio  <br/> Office 365 portal, autenticación Office 365, &amp; Office en un explorador  <br/> | Solicitudes DNS, CRL y &amp; CDN  <br/>  Todos los demás servicios de Office 365 no se admiten específicamente a través de Azure ExpressRoute  <br/>  Todos los demás servicios en la nube de Microsoft  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Consideraciones clave de planeamiento para el uso de comunidades BGP

Los clientes que decidan aprovechar las comunidades BGP para influir en la forma en que ExpressRoute se anuncia y propaga a través de la red de clientes deben tener en cuenta las siguientes consideraciones:
  
- Cuando se usan comunidades BGP en el diseño de red, es importante asegurarse de que se mantiene la simetría de rutas. En algunos casos, la adición o eliminación de comunidades BGP puede crear una situación en la que el enrutamiento simétrico se interrumpe y la configuración de enrutamiento debe actualizarse para volver a establecer el enrutamiento simétrico.

- El ámbito de Azure ExpressRoute con valores de comunidad BGP es una acción del cliente. Microsoft anunciará todos los prefijos IP asociados a la relación de emparejamiento independientemente de cualquier ámbito configurado por el cliente.

- Azure ExpressRoute no admite ninguna acción en la red de Microsoft en función de las comunidades BGP asignadas por el cliente.

- Los prefijos IP usados por Office 365 solo se marcan con valores de comunidad BGP específicos del servicio, no se admiten comunidades BGP específicas de ubicación. Office 365 servicios son globales por naturaleza, no se admiten los prefijos de filtrado en función de la ubicación del inquilino o de los datos dentro de la nube de Office 365. El enfoque recomendado es configurar la red para coordinar la ruta de acceso de red más corta o preferida desde la ubicación de red del usuario a la red global de Microsoft, independientemente de la ubicación física de la dirección IP del servicio Office 365 que solicite.

- Los prefijos IP incluidos en cada valor de comunidad BGP representan una subred que contiene direcciones IP para la aplicación Office 365 asociada al valor. En algunos casos, más de una aplicación Office 365 tiene direcciones IP dentro de una subred, lo que da lugar a un prefijo IP existente en más de un valor de comunidad. Esto se espera, aunque rara vez, comportamiento debido a la fragmentación de asignación y no afecta al recuento de prefijos ni a los objetivos de administración de ancho de banda. Se recomienda a los clientes que usen el enfoque "permitir lo que se necesita" en lugar de "denegar lo que no es necesario" al aprovechar las comunidades BGP para Office 365 para minimizar el efecto.

- El uso de comunidades BGP no cambia los requisitos de conectividad de red subyacentes ni la configuración necesaria para usar Office 365. Los clientes que quieran acceder a Office 365 siguen siendo necesarios para poder acceder a Internet.

- El ámbito de Azure ExpressRoute con comunidades BGP solo afecta a las rutas que la red interna puede ver a través de la relación de emparejamiento de Microsoft. Es posible que tenga que realizar configuraciones adicionales de nivel de aplicación, como el uso de una configuración PAC o WPAD junto con el enrutamiento con ámbito.

- Además de usar las comunidades BGP asignadas por Microsoft, los clientes pueden optar por asignar sus propias comunidades BGP a Office 365 prefijos IP aprendidos a través de Azure ExpressRoute para influir en el enrutamiento interno. Un caso de uso popular es asignar una comunidad BGP basada en ubicación a todas las rutas aprendidas a través de cada ubicación de emparejamiento de ExpressRoute determinada y, a continuación, usar esa información de bajada en la red del cliente para coordinar la ruta de acceso de red más corta o preferida en la red de Microsoft. El uso de comunidades BGP asignadas por el cliente con ExpressRoute para escenarios de Office 365 está fuera del ámbito de control o visibilidad de Microsoft.

Este es un breve vínculo que puede usar para volver: [https://aka.ms/bgpexpressroute365]().
  
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