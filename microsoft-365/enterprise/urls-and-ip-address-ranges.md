---
title: Intervalos de direcciones IP y URL de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/28/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
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
description: 'Resumen: Office 365 necesita conectividad a Internet. Los siguientes puntos de conexión deben resultar accesibles para los clientes que usan planes de Office 365, incluida la nube de la comunidad de administración pública (GCC).'
hideEdit: true
ms.openlocfilehash: 6a2521ac872eb76a327ceb659814b42d5495ddb3
ms.sourcegitcommit: 8aa110806572e9b19682c8f97ee4bf3953e1fd3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/09/2022
ms.locfileid: "67294509"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Intervalos de direcciones IP y direcciones URL de Office 365

Office 365 requiere conectividad a Internet. Los siguientes puntos de conexión deberían ser accesibles para los clientes que usan planes de Office 365, incluyendo los planes Government Community Cloud (GCC).
  
*Office 365 mundial (+GCC)* \| [Office 365 operado por 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|

|Notas|Descargar|Utilice|
|---|---|---|
|**Última actualización:** 28/07/2022: ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del registro de cambios](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).|**Use:** nuestros [archivos PAC](managing-office-365-endpoints.md#pacfiles) de proxy|
|

Comience por [Administrar los puntos de conexión de Office 365](managing-office-365-endpoints.md) si desea entender nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan según sea necesario al principio de cada mes, con nuevas direcciones IP y direcciones URL publicadas 30 días antes de estar activos. Esta cadencia permite a los clientes que aún no tienen actualizaciones automatizadas completar sus procesos antes de que se requiera una nueva conectividad. Los puntos de conexión también se pueden actualizar durante el mes, si es necesario, para abordar las escalaciones de soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que se muestran en la página siguiente se generan a partir de los servicios web basados en REST. Si usa un script o un dispositivo de red para acceder a estos datos, debe ir directamente al [servicio web](microsoft-365-ip-web-service.md).

Los datos de puntos de conexión siguientes enumeran los requisitos de conectividad desde el equipo de un usuario a Office 365. Para obtener detalles sobre las direcciones IP usadas para las conexiones de red de Microsoft a una red de cliente, a veces denominadas conexiones de red híbridas o entrantes, consulte [Puntos de conexión adicionales](additional-office365-ip-addresses-and-urls.md) para obtener más información.

Los puntos de conexión se agrupan en cuatro áreas de servicio que representan las tres cargas de trabajo principales y un conjunto de recursos comunes. Los grupos pueden usarse para asociar flujos de tráfico con una aplicación determinada, pero dado que las características suelen consumir puntos de conexión en varias cargas de trabajo, estos grupos no se pueden usar para restringir el acceso de manera eficaz.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como **Optimizar**, **Permitir** o **Predeterminado**. Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

   Puede leer sobre estas categorías e instrucciones para su administración en [Nuevas categorías de puntos de conexión de Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).

- **ER**: esto es **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad BGP que incluye los prefijos de ruta mostrados se alinea con el área de servicio indicada. Cuando ER es **No**, esto significa que ExpressRoute no se admite para este conjunto de puntos de conexión.

   Algunas rutas se pueden anunciar en más de una comunidad BGP, lo que permite que los puntos de conexión dentro de un intervalo IP determinado atraviesen el circuito de ER; sin embargo, aún no se admiten. En todos los casos, se debe respetar el valor de la columna ER de un conjunto de puntos de conexión determinado. Para obtener más información sobre las comunidades BGP, consulte [Usar comunidades BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md#key-planning-considerations-to-using-bgp-communities).

- **Direcciones**: muestra los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.

- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones IP enumeradas para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.

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
