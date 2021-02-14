---
title: Administración de la conectividad de ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Obtenga información sobre cómo administrar ExpressRoute para Office 365, incluidas las áreas comunes para configurar como el filtrado de prefijos, la seguridad y el cumplimiento.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694227"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Administración de la conectividad de ExpressRoute para Office 365

ExpressRoute para Office 365 ofrece una ruta de enrutamiento alternativa para llegar a muchos servicios de Office 365 sin necesidad de todo el tráfico para salir a Internet. Aunque la conexión a Internet a Office 365 sigue siendo necesaria, las rutas específicas que Microsoft anuncia a través de BGP a la red hacen que el circuito directo de ExpressRoute prefiera a menos que haya otras configuraciones en la red. Las tres áreas comunes que puede configurar para administrar este enrutamiento incluyen el filtrado de prefijos, la seguridad y el cumplimiento.
  
> [!NOTE]
> Microsoft cambió la forma en que se revisa el dominio de enrutamiento de emparejamiento de Microsoft para Azure ExpressRoute. A partir del 31 de julio de 2017, todos los clientes de Azure ExpressRoute pueden habilitar el emparejamiento de Microsoft directamente desde la consola administrativa de Azure o a través de PowerShell. Después de habilitar El emparejamiento de Microsoft, cualquier cliente puede crear filtros de ruta para recibir anuncios de ruta BGP para aplicaciones dynamics 365 Customer Engagement (anteriormente conocidas como CRM Online). Los clientes que necesitan Azure ExpressRoute para Office 365 deben obtener la opinión de Microsoft antes de poder crear filtros de ruta para Office 365. Póngase en contacto con su equipo de cuenta de Microsoft para obtener información sobre cómo solicitar una revisión para habilitar Office 365 ExpressRoute. Las suscripciones no autorizadas que intentan crear filtros de ruta para Office 365 recibirán un [mensaje de error](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Filtrado de prefijos

Microsoft recomienda que los clientes acepten todas las rutas BGP como se anuncia desde Microsoft, las rutas proporcionadas se someten a un riguroso proceso de revisión y validación, lo que elimina los beneficios de la inspección adicional. ExpressRoute ofrece de forma nativa los controles recomendados, como la propiedad del prefijo IP, la integridad y la escala, sin filtrado de rutas entrantes en el lado del cliente.
  
Si necesita una validación adicional de la propiedad de la ruta en el emparejamiento público de ExpressRoute, puede comprobar las rutas anunciadas con la lista de todos los prefijos IP IPv4 e IPv6 que representan los [intervalos IP públicos](https://www.microsoft.com/download/details.aspx?id=53602)de Microsoft. Estos intervalos cubren todo el espacio de direcciones de Microsoft y cambian con poca frecuencia, lo que proporciona un conjunto confiable de intervalos para filtrar, lo que también proporciona protección adicional a los clientes que están interesados en que las rutas que no son de Microsoft se filtren en su entorno. En caso de que haya un cambio, se realizará el 1 del  mes y el número de versión de la sección de detalles de la página cambiará cada vez que se actualice el archivo.
  
Existen varias razones para evitar el uso de las direcciones URL e intervalos de direcciones IP de [Office 365](https://aka.ms/o365endpoints) para generar listas de filtros de prefijos. Incluye lo siguiente:
  
- Los prefijos IP de Office 365 experimentan una gran cantidad de cambios con frecuencia.

- Las direcciones URL e intervalos de direcciones IP de Office 365 están diseñadas para administrar listas de permitidos de firewall e infraestructura de proxy, no para enrutamiento.

- Las direcciones URL e intervalos de direcciones IP de Office 365 no cubren otros servicios de Microsoft que puedan estar en el ámbito de las conexiones de ExpressRoute.

|**Opción**|**Complejidad**|**Control de cambios**|
|:-----|:-----|:-----|
|Aceptar todas las rutas de Microsoft  <br/> |**Bajo:** El cliente depende de los controles de Microsoft para garantizar que todas las rutas son propiedad correcta.  <br/> |Ninguno  <br/> |
|Filtrar supernets pertenecientes a Microsoft  <br/> |**Medio:** El cliente implementa listas resumida de filtros de prefijos para permitir solo rutas propiedad de Microsoft.  <br/> |Los clientes deben asegurarse de que las actualizaciones con poca frecuencia se reflejan en los filtros de ruta.  <br/> |
|Filtrar intervalos IP de Office 365  <br/> [!CAUTION] Not-Recommended |**Alto:** El cliente filtra rutas basadas en prefijos IP de Office 365 definidos.  <br/> |Los clientes deben implementar un sólido proceso de administración de cambios para las actualizaciones mensuales.  <br/> [!CAUTION] Esta solución requiere cambios importantes en el tiempo. Los cambios no implementados en el tiempo probablemente provocarán una interrupción del servicio.   |

La conexión a Office 365 con Azure ExpressRoute se basa en anuncios BGP de subredes IP específicas que representan redes donde se implementan puntos de conexión de Office 365. Debido a la naturaleza global de Office 365 y al número de servicios que forma Office 365, los clientes a menudo tienen que administrar los anuncios que aceptan en su red. Si le preocupa el número de prefijos que se anuncian en su entorno, la característica de la comunidad [BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) le permite filtrar los anuncios a un conjunto específico de servicios de Office 365. Esta característica está ahora en versión preliminar.
  
Independientemente de cómo administre los anuncios de ruta BGP procedentes de Microsoft, no obtendrá ninguna exposición especial a los servicios de Office 365 en comparación con conectarse a Office 365 solo a través de un circuito de Internet. Microsoft mantiene los mismos niveles de seguridad, cumplimiento y rendimiento, independientemente del tipo de circuito que un cliente use para conectarse a Office 365.
  
### <a name="security"></a>Seguridad

Microsoft recomienda mantener sus propios controles perimetrales de red y seguridad para las conexiones que van a y desde ExpressRoute público y emparejamiento de Microsoft, que incluye conexiones desde y hacia los servicios de Office 365. Los controles de seguridad deben estar en su lugar para las solicitudes de red que viajan desde su red a la red de Microsoft, así como entrantes desde la red de Microsoft a su red.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Salida de cliente a Microsoft
  
Cuando los equipos se conectan a Office 365, se conectan al mismo conjunto de puntos de conexión independientemente de si la conexión se realiza a través de un circuito de Internet o ExpressRoute. Independientemente del circuito que se esté utilizando, Microsoft recomienda tratar los servicios de Office 365 como destinos de Internet más confiables que los genéricos. Los controles de seguridad salientes deben centrarse en los puertos y protocolos para reducir la exposición y minimizar el mantenimiento continuo. La información de puerto necesaria está disponible en el artículo de referencia de puntos de conexión de [Office 365.](https://aka.ms/o365endpoints)
  
Para controles agregados, puede usar el filtrado de nivel de FQDN dentro de la infraestructura de proxy para restringir o inspeccionar algunas o todas las solicitudes de red destinadas a Internet u Office 365. Mantener la lista de FQDN a medida que se publican las características y que las ofertas de Office 365 evolucionan requiere una administración de cambios más sólida y un seguimiento de los cambios en los puntos de conexión de [Office 365 publicados.](https://aka.ms/o365endpoints)
  
> [!CAUTION]
> Microsoft recomienda que no se base únicamente en prefijos IP para administrar la seguridad saliente en Office 365.

|**Opción**|**Complejidad**|**Control de cambios**|
|:-----|:-----|:-----|
|Sin restricciones  <br/> |**Bajo:** El cliente permite el acceso saliente sin restricciones a Microsoft.  <br/> |Ninguno  <br/> |
|Restricciones de puerto  <br/> |**Bajo:** El cliente restringe el acceso saliente a Microsoft por los puertos esperados.  <br/> |Poco frecuente.  <br/> |
|Restricciones de FQDN  <br/> |**Alto:** El cliente restringe el acceso saliente a Office 365 en función de los FQDN publicados.  <br/> |Cambios mensuales.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Entrante de Microsoft al cliente
  
Hay varios escenarios opcionales que requieren que Microsoft inicie conexiones a la red.
  
- ADFS durante la validación de contraseña para el inicio de sesión.

- [Exchange Server implementaciones híbridas.](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)

- Correo de un inquilino de Exchange Online a un host local.

- El correo de SharePoint Online envía desde SharePoint Online a un host local.

- [Búsqueda híbrida federada de SharePoint.](https://technet.microsoft.com/library/dn197174.aspx)

- [BCS híbrido de SharePoint.](https://technet.microsoft.com/library/dn197239.aspx )

- [Skype Empresarial híbrido o](https://technet.microsoft.com/library/jj205403.aspx) federación [de Skype Empresarial.](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx)

- [Skype Empresarial Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

Microsoft recomienda que acepte estas conexiones a través del circuito de Internet en lugar del circuito de ExpressRoute para reducir la complejidad. Si sus necesidades de cumplimiento o rendimiento determinan que estas conexiones entrantes deben aceptarse a través de un circuito de ExpressRoute, se recomienda usar un firewall o proxy inverso para establecer el ámbito de las conexiones aceptadas. Puede usar los puntos [de conexión de Office 365](https://aka.ms/o365endpoints) para averiguar los FQDN y prefijos IP correctos.
  
### <a name="compliance"></a>Cumplimiento

No dependemos de la ruta de enrutamiento que use para ninguno de nuestros controles de cumplimiento. Independientemente de si se conecta a los servicios de Office 365 a través de ExpressRoute o un circuito de Internet, nuestros controles de cumplimiento no cambiarán. Debe revisar los distintos niveles de certificación de cumplimiento y seguridad de Office 365 para averiguar la mejor opción para satisfacer las necesidades de su organización.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Temas relacionados

[Redes de entrega de contenido](content-delivery-networks.md)
  
[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Aprendizaje de Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer)
