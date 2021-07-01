---
title: Intervalos de direcciones IP y URL de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/28/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
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
ms.openlocfilehash: 99a58e1f520c7f22fcb0d78a7d4b7e400b5ed87d
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203141"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="a69ba-104">Intervalos de direcciones IP y direcciones URL de Office 365</span><span class="sxs-lookup"><span data-stu-id="a69ba-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="a69ba-p102">Office 365 requiere conectividad a Internet. Los siguientes puntos de conexión deberían ser accesibles para los clientes que usan planes de Office 365, incluyendo los planes Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="a69ba-p102">Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="a69ba-107">*Office 365 mundial (incluido GCC)* | [Office 365 operado por 21Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="a69ba-107">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="a69ba-108">**Última actualización:** 28/06/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del Registro de cambios](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="a69ba-108">**Last updated:** 06/28/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span> <br/> |<span data-ttu-id="a69ba-109">**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="a69ba-109">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> | <span data-ttu-id="a69ba-110">**Use:** nuestros [archivos PAC](managing-office-365-endpoints.md#pacfiles) de proxy</span><span class="sxs-lookup"><span data-stu-id="a69ba-110">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |

 <span data-ttu-id="a69ba-p103">Comience por [Administrar los puntos de conexión de Office 365](managing-office-365-endpoints.md) si desea entender nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan al principio de cada mes, según sea necesario, con las nuevas direcciones IP y URL publicadas 30 días antes de su activación. Esto permite que los clientes que todavía no hayan automatizado las actualizaciones completen el proceso antes de que se requiera una nueva conectividad. También podrían actualizarse los puntos de conexión durante el mes, si fuera necesario, para gestionar la canalización del soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que aparecen en la página siguiente se generan desde los servicios web basados en REST. Si usa un dispositivo de red o un script para obtener acceso a estos datos, vaya directamente al [Servicio web](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="a69ba-p103">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated as needed at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="a69ba-p104">Los siguientes datos de puntos de conexión enumeran los requisitos para la conectividad del equipo de un usuario a Office 365. No incluye las conexiones de red de Microsoft a una red de clientes, a veces denominadas conexiones de red de entrada o híbridas. Vea [Puntos de conexión adicionales](additional-office365-ip-addresses-and-urls.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p104">Endpoint data below lists requirements for connectivity from a user's machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections. See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="a69ba-p105">Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p105">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="a69ba-123">Estas son columnas de datos que se muestran:</span><span class="sxs-lookup"><span data-stu-id="a69ba-123">Data columns shown are:</span></span>

- <span data-ttu-id="a69ba-p106">**ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p106">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="a69ba-p107">**Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer sobre estas categorías y encontrar indicaciones para su administración en [Las nuevas categorías de punto de conexión de Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p107">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default". You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="a69ba-p108">**EMERGENCIA**: aparece como **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad de BGP que incluye los prefijos de ruta que aparecen se alinea con el área de servicio que se muestra. Si EMERGENCIA aparece como **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe dar por hecho que no se anuncia ninguna ruta para un conjunto de puntos de conexión cuando EMERGENCIA se establezca como **No**.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p108">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="a69ba-p109">**Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p109">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="a69ba-p110">**Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.</span><span class="sxs-lookup"><span data-stu-id="a69ba-p110">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
><span data-ttu-id="a69ba-139">Para obtener recomendaciones sobre direcciones IP y URL de Yammer, consulte [El uso de direcciones IP codificadas de forma rígida para Yammer no es recomendable](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) en el blog de Yammer.</span><span class="sxs-lookup"><span data-stu-id="a69ba-139">For recommendations on Yammer IP addresses and URLs, see [Using hard-coded IP addresses for Yammer is not recommended](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) on the Yammer blog.</span></span>
>

## <a name="related-topics"></a><span data-ttu-id="a69ba-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a69ba-140">Related Topics</span></span>
[<span data-ttu-id="a69ba-141">Puntos de conexión adicionales no incluidos en el servicio web de URL ni en la dirección IP de Office 365</span><span class="sxs-lookup"><span data-stu-id="a69ba-141">Additional endpoints not included in the Office 365 IP Address and URL Web service</span></span>](additional-office365-ip-addresses-and-urls.md)

[<span data-ttu-id="a69ba-142">Administrar puntos de conexión de Office 365</span><span class="sxs-lookup"><span data-stu-id="a69ba-142">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="a69ba-143">Puntos de conexión generales de Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="a69ba-143">General Microsoft Stream endpoints</span></span>](/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="a69ba-144">Supervisar la conectividad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a69ba-144">Monitor Microsoft 365 connectivity</span></span>](./monitor-connectivity.md)

[<span data-ttu-id="a69ba-145">Entidad de certificación raíz y el paquete de entidad de certificación intermedia en el sistema de aplicación de terceros</span><span class="sxs-lookup"><span data-stu-id="a69ba-145">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="a69ba-146">Conectividad de clientes</span><span class="sxs-lookup"><span data-stu-id="a69ba-146">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="a69ba-147">Redes de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="a69ba-147">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="a69ba-148">Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube pública</span><span class="sxs-lookup"><span data-stu-id="a69ba-148">Microsoft Azure IP Ranges and Service Tags – Public Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=56519)

[<span data-ttu-id="a69ba-149">Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de administración pública de EUA</span><span class="sxs-lookup"><span data-stu-id="a69ba-149">Microsoft Azure IP Ranges and Service Tags – US Government Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57063)

[<span data-ttu-id="a69ba-150">Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de Alemania</span><span class="sxs-lookup"><span data-stu-id="a69ba-150">Microsoft Azure IP Ranges and Service Tags – Germany Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57064)

[<span data-ttu-id="a69ba-151">Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de China</span><span class="sxs-lookup"><span data-stu-id="a69ba-151">Microsoft Azure IP Ranges and Service Tags – China Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57062)
  
[<span data-ttu-id="a69ba-152">Espacio IP público de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a69ba-152">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)

[<span data-ttu-id="a69ba-153">Registro de nombre de servicio y número de puerto del protocolo de transporte</span><span class="sxs-lookup"><span data-stu-id="a69ba-153">Service Name and Transport Protocol Port Number Registry</span></span>](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
