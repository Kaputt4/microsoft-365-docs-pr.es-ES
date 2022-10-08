---
title: Intervalos de direcciones IP y URL de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/29/2022
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Summary: Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: b52c3a4e197fa69e8db85e6ea1a542dd754b16f1
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191854"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Intervalos de direcciones IP y direcciones URL de Office 365

Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).
  
*Office 365 mundial (+GCC)* \| [Office 365 operado por 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|

|Notas|Descargar|Utilice|
|---|---|---|
|**Última actualización:** 29/09/2022 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del registro de cambios](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).|**Use:** nuestros [archivos PAC](managing-office-365-endpoints.md#pacfiles) de proxy|
|

Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated as needed at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This cadence allows for customers who don't yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you're using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.

Los datos de puntos de conexión siguientes enumeran los requisitos de conectividad desde el equipo de un usuario a Office 365. Para obtener detalles sobre las direcciones IP usadas para las conexiones de red de Microsoft a una red de cliente, a veces denominadas conexiones de red híbridas o entrantes, consulte [Puntos de conexión adicionales](additional-office365-ip-addresses-and-urls.md) para obtener más información.

Los puntos de conexión se agrupan en cuatro áreas de servicio que representan las tres cargas de trabajo principales y un conjunto de recursos comunes. Los grupos pueden usarse para asociar flujos de tráfico con una aplicación determinada, pero dado que las características suelen consumir puntos de conexión en varias cargas de trabajo, estos grupos no se pueden usar para restringir el acceso de manera eficaz.

Estas son columnas de datos que se muestran:

- **ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.

- **Category**: Shows whether the endpoint set is categorized as **Optimize**, **Allow**, or **Default**. This column also lists which endpoint sets are required to have network connectivity. For endpoint sets that aren't required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you're excluding an entire service area, the endpoint sets listed as required don't require connectivity.

   Puede leer sobre estas categorías e instrucciones para su administración en [Nuevas categorías de puntos de conexión de Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).

- **ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set.

   Algunas rutas se pueden anunciar en más de una comunidad BGP, lo que permite que los puntos de conexión dentro de un intervalo IP determinado atraviesen el circuito de ER; sin embargo, aún no se admiten. En todos los casos, se debe respetar el valor de la columna ER de un conjunto de puntos de conexión determinado. Para obtener más información sobre las comunidades BGP, consulte [Usar comunidades BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md#key-planning-considerations-to-using-bgp-communities).

- **Addresses**: Lists the FQDNs or wildcard domain names and IP address ranges for the endpoint set. Note that an IP address range is in CIDR format and may include many individual IP addresses in the specified network.

- **Ports**: Lists the TCP or UDP ports that are combined with listed IP addresses to form the network endpoint. You may notice some duplication in IP address ranges where there are different ports listed.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> Para obtener recomendaciones sobre direcciones IP y URL de Yammer, consulte [El uso de direcciones IP codificadas de forma rígida para Yammer no es recomendable](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) en el blog de Yammer.

## <a name="related-topics"></a>Temas relacionados

[Puntos de conexión adicionales no incluidos en el servicio web de URL ni en la dirección IP de Office 365](additional-office365-ip-addresses-and-urls.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Puntos de conexión generales de Microsoft Stream](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Supervisar la conectividad de Microsoft 365](./monitor-connectivity.md)

[Entidad de certificación raíz y el paquete de entidad de certificación intermedia en el sistema de aplicación de terceros](../compliance/encryption-office-365-certificate-chains.md)
  
[Conectividad de clientes](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Redes de entrega de contenido](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube pública](https://www.microsoft.com/download/details.aspx?id=56519)

[Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de administración pública de EUA](https://www.microsoft.com/download/details.aspx?id=57063)

[Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de China](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Espacio IP público de Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)

[Registro de nombre de servicio y número de puerto del protocolo de transporte](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
