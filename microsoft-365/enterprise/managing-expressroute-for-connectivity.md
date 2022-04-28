---
title: Administración de la conectividad de ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Obtenga información sobre cómo administrar ExpressRoute para Office 365, incluidas las áreas comunes para configurar, como el filtrado de prefijos, la seguridad y el cumplimiento.
ms.openlocfilehash: a601c047a7b8e19f02a728d00708689c795d5a64
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098326"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Administración de la conectividad de ExpressRoute para Office 365

ExpressRoute para Office 365 ofrece una ruta de acceso de enrutamiento alternativa para llegar a muchos servicios Office 365 sin necesidad de todo el tráfico de salida a Internet. Aunque la conexión a Internet a Office 365 sigue siendo necesaria, las rutas específicas que Microsoft anuncia a través de BGP a la red hacen que se prefiera el circuito ExpressRoute directo a menos que haya otras configuraciones en la red. Las tres áreas comunes que puede que desee configurar para administrar este enrutamiento incluyen el filtrado de prefijos, la seguridad y el cumplimiento.
  
> [!NOTE]
> Microsoft cambió la forma en que se revisa el dominio de enrutamiento de emparejamiento de Microsoft para Azure ExpressRoute. A partir del 31 de julio de 2017, todos los clientes de Azure ExpressRoute pueden habilitar el emparejamiento de Microsoft directamente desde la consola de Administración de Azure o a través de PowerShell. Después de habilitar el emparejamiento de Microsoft, cualquier cliente puede crear filtros de ruta para recibir anuncios de ruta BGP para aplicaciones de Dynamics 365 Customer Engagement (anteriormente conocidas como CRM Online). Los clientes que necesitan Azure ExpressRoute para Office 365 deben obtener la revisión de Microsoft para poder crear filtros de ruta para Office 365. Póngase en contacto con el equipo de su cuenta microsoft para obtener información sobre cómo solicitar una revisión para habilitar Office 365 ExpressRoute. Las suscripciones no autorizadas que intentan crear filtros de ruta para Office 365 recibirán un [mensaje de error](https://support.microsoft.com/kb/3181709).
  
## <a name="prefix-filtering"></a>Filtrado de prefijos

Microsoft recomienda que los clientes acepten todas las rutas BGP tal y como se anuncian desde Microsoft; las rutas proporcionadas se someten a un riguroso proceso de revisión y validación, lo que elimina las ventajas de un examen adicional. ExpressRoute ofrece de forma nativa los controles recomendados, como la propiedad, la integridad y la escala del prefijo IP, sin filtrado de rutas de entrada en el lado del cliente.
  
Si necesita una validación adicional de la propiedad de la ruta en el emparejamiento público de ExpressRoute, puede comprobar las rutas anunciadas en la lista de todos los prefijos IP IPv4 e IPv6 que representan [los intervalos ip públicos de Microsoft](https://www.microsoft.com/download/details.aspx?id=53602). Estos intervalos cubren todo el espacio de direcciones de Microsoft y cambian con poca frecuencia, lo que proporciona un conjunto confiable de intervalos con los que filtrar que también proporciona protección adicional a los clientes que están preocupados por la pérdida de rutas que no son propiedad de Microsoft en su entorno. En caso de que se produzca un cambio, se realizará el 1 de mes y el número de versión de la sección **de detalles** de la página cambiará cada vez que se actualice el archivo.
  
Hay varias razones para evitar el uso de las [direcciones URL de Office 365 y los intervalos de direcciones IP](./urls-and-ip-address-ranges.md) para generar listas de filtros de prefijos. Incluido lo siguiente:
  
- Los prefijos IP de Office 365 experimentan muchos cambios con frecuencia.

- Las direcciones URL Office 365 y los intervalos de direcciones IP están diseñadas para administrar las listas de permitidos de firewall y la infraestructura de proxy, no para el enrutamiento.

- Las direcciones URL de Office 365 y los intervalos de direcciones IP no cubren otros servicios Microsoft que puedan estar en el ámbito de las conexiones de ExpressRoute.

|**Opción**|**Complejidad**|**Cambiar control**|
|:-----|:-----|:-----|
|Aceptar todas las rutas de Microsoft  <br/> |**Bajo:** El cliente se basa en los controles de Microsoft para asegurarse de que todas las rutas son propiedad correcta.  <br/> |Ninguno  <br/> |
|Filtrar supernets propiedad de Microsoft  <br/> |**Medio:** El cliente implementa listas de filtros de prefijos resumidos para permitir solo rutas propiedad de Microsoft.  <br/> |Los clientes deben asegurarse de que las actualizaciones poco frecuentes se reflejan en los filtros de ruta.  <br/> |
|Filtrar intervalos IP Office 365  <br/> [!CAUTION] Not-Recommended |**Alto:** El cliente filtra las rutas en función de los prefijos IP de Office 365 definidos.  <br/> |Los clientes deben implementar un sólido proceso de administración de cambios para las actualizaciones mensuales.  <br/> [!CAUTION] Esta solución requiere cambios significativos. Es probable que los cambios no implementados a tiempo produzcan una interrupción del servicio.   |

La conexión a Office 365 mediante Azure ExpressRoute se basa en anuncios BGP de subredes IP específicas que representan redes donde se implementan Office 365 puntos de conexión. Debido a la naturaleza global de Office 365 y al número de servicios que componen Office 365, los clientes a menudo tienen la necesidad de administrar los anuncios que aceptan en su red. Si le preocupa el número de prefijos anunciados en su entorno, la característica de [la comunidad BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) le permite filtrar los anuncios a un conjunto específico de servicios de Office 365. Esta característica está ahora en versión preliminar.
  
Independientemente de cómo administre los anuncios de ruta BGP procedentes de Microsoft, no obtendrá ninguna exposición especial a Office 365 servicios en comparación con la conexión a Office 365 solo a través de un circuito de Internet. Microsoft mantiene los mismos niveles de seguridad, cumplimiento y rendimiento, independientemente del tipo de circuito que use un cliente para conectarse a Office 365.
  
### <a name="security"></a>Seguridad

Microsoft recomienda mantener sus propios controles perimetrales de red y seguridad para las conexiones que van hacia y desde ExpressRoute público y el emparejamiento de Microsoft, lo que incluye conexiones hacia y desde Office 365 servicios. Los controles de seguridad deben estar implementados para las solicitudes de red que viajan salientes desde la red a la red de Microsoft, así como para la entrada desde la red de Microsoft a la red.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Salida del cliente a Microsoft
  
Cuando los equipos se conectan a Office 365, se conectan al mismo conjunto de puntos de conexión, independientemente de si la conexión se realiza a través de Internet o un circuito ExpressRoute. Independientemente del circuito que se use, Microsoft recomienda tratar Office 365 servicios como destinos de Internet más confiables que genéricos. Los controles de seguridad salientes deben centrarse en los puertos y protocolos para reducir la exposición y minimizar el mantenimiento continuo. La información de puerto necesaria está disponible en el artículo de referencia [Office 365 puntos de conexión](./urls-and-ip-address-ranges.md).
  
Para los controles agregados, puede usar el filtrado de nivel de FQDN dentro de la infraestructura de proxy para restringir o inspeccionar algunas o todas las solicitudes de red destinadas a Internet o Office 365. Mantener la lista de FQDN a medida que se publican las características y las ofertas de Office 365 evolucionan requiere una administración de cambios más sólida y un seguimiento de los cambios en los [puntos de conexión de Office 365 publicados](./urls-and-ip-address-ranges.md).
  
> [!CAUTION]
> Microsoft recomienda que no se base únicamente en prefijos IP para administrar la seguridad de salida a Office 365.

|**Opción**|**Complejidad**|**Cambiar control**|
|:-----|:-----|:-----|
|Sin restricciones  <br/> |**Bajo:** El cliente permite el acceso saliente sin restricciones a Microsoft.  <br/> |Ninguno  <br/> |
|Restricciones de puerto  <br/> |**Bajo:** El cliente restringe el acceso saliente a Microsoft por los puertos esperados.  <br/> |Infrecuente.  <br/> |
|Restricciones de FQDN  <br/> |**Alto:** El cliente restringe el acceso saliente a Office 365 en función de los FQDN publicados.  <br/> |Cambios mensuales.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Entrada de Microsoft al cliente
  
Hay varios escenarios opcionales que requieren que Microsoft inicie conexiones a la red.
  
- ADFS durante la validación de contraseñas para el inicio de sesión.

- [Exchange Server implementaciones híbridas](/exchange/exchange-hybrid).

- Envíe correo desde un inquilino de Exchange Online a un host local.

- SharePoint envío de correo en línea desde SharePoint Online a un host local.

- [SharePoint búsqueda híbrida federada](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [SharePoint BCS híbrido](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype Empresarial federación híbrida](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) o [Skype Empresarial](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype Empresarial Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Microsoft recomienda aceptar estas conexiones a través del circuito de Internet en lugar del circuito ExpressRoute para reducir la complejidad. Si las necesidades de cumplimiento o rendimiento determinan que estas conexiones entrantes se deben aceptar a través de un circuito ExpressRoute, se recomienda usar un firewall o un proxy inverso para limitar las conexiones aceptadas. Puede usar los [puntos de conexión de Office 365](./urls-and-ip-address-ranges.md) para averiguar los FQDN y prefijos IP adecuados.
  
### <a name="compliance"></a>Cumplimiento

No nos basamos en la ruta de enrutamiento que se usa para ninguno de nuestros controles de cumplimiento. Independientemente de si se conecta a Office 365 servicios a través de un circuito ExpressRoute o internet, nuestros controles de cumplimiento no cambiarán. Debe revisar los distintos niveles de certificación de cumplimiento y seguridad de Office 365 para averiguar cuál es la mejor opción para satisfacer las necesidades de su organización.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>Temas relacionados

[Redes de entrega de contenido](content-delivery-networks.md)
  
[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Aprendizaje de Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer)