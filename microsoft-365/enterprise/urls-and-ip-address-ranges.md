---
title: Intervalos de direcciones IP y URL de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
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
ms.openlocfilehash: 48be058cb48e99b9b573cc4211561dfe8e5cc6e8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730155"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Intervalos de direcciones IP y direcciones URL de Office 365

Office 365 requiere conectividad a Internet. Los siguientes puntos de conexión deberían ser accesibles para los clientes que usan planes de Office 365, incluyendo los planes Government Community Cloud (GCC).
  
*Office 365 mundial (incluido GCC)* | [Office 365 operado por 21Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**Última actualización:** 28/05/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del Registro de cambios](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> | **Use:** nuestros [archivos PAC](managing-office-365-endpoints.md#pacfiles) de proxy <br/> |

 Comience por [Administrar los puntos de conexión de Office 365](managing-office-365-endpoints.md) si desea entender nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan al principio de cada mes, según sea necesario, con las nuevas direcciones IP y URL publicadas 30 días antes de su activación. Esto permite que los clientes que todavía no hayan automatizado las actualizaciones completen el proceso antes de que se requiera una nueva conectividad. También podrían actualizarse los puntos de conexión durante el mes, si fuera necesario, para gestionar la canalización del soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que aparecen en la página siguiente se generan desde los servicios web basados en REST. Si usa un dispositivo de red o un script para obtener acceso a estos datos, vaya directamente al [Servicio web](microsoft-365-ip-web-service.md).

Los siguientes datos de puntos de conexión enumeran los requisitos para la conectividad del equipo de un usuario a Office 365. No incluye las conexiones de red de Microsoft a una red de clientes, a veces denominadas conexiones de red de entrada o híbridas. Vea [Puntos de conexión adicionales](additional-office365-ip-addresses-and-urls.md) para obtener más información.

Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer sobre estas categorías y encontrar indicaciones para su administración en [Las nuevas categorías de punto de conexión de Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

- **EMERGENCIA**: aparece como **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad de BGP que incluye los prefijos de ruta que aparecen se alinea con el área de servicio que se muestra. Si EMERGENCIA aparece como **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe dar por hecho que no se anuncia ninguna ruta para un conjunto de puntos de conexión cuando EMERGENCIA se establezca como **No**.

- **Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.
 
- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>Para obtener recomendaciones sobre direcciones IP y URL de Yammer, consulte [El uso de direcciones IP codificadas de forma rígida para Yammer no es recomendable](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) en el blog de Yammer.
>

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

[Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de Alemania](https://www.microsoft.com/download/details.aspx?id=57064)

[Rangos de IP de Microsoft Azure y etiquetas de servicio: Nube de China](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Espacio IP público de Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)

[Registro de nombre de servicio y número de puerto del protocolo de transporte](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
