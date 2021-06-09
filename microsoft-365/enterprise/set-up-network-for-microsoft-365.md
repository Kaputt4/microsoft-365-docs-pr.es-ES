---
title: Configurar la red para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Busque vínculos a artículos con información que le ayuden a configurar la red para Microsoft 365, incluida una introducción a la conectividad de red y una lista de puntos de conexión.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693682"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Configurar la red para Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Una parte importante de la incorporación Microsoft 365 es garantizar que las conexiones de red e Internet estén configuradas para un acceso optimizado. La configuración de la red local para tener acceso a una nube de Software como servicio (SaaS) distribuida globalmente es diferente de una red tradicional optimizada para el tráfico a centros de datos locales y una conexión central a Internet. 

Use estos artículos para comprender las principales diferencias, así como para modificar los dispositivos perimetrales, los equipos cliente y la red local a fin de obtener el mejor rendimiento para sus usuarios locales.

## <a name="how-microsoft-365-networking-works"></a>Cómo Microsoft 365 de red

Vea estos artículos para obtener información general sobre la conectividad para Microsoft 365:

- [Información general de conectividad de red de Microsoft 365](microsoft-365-networking-overview.md)
- [Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)
- [Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

Para obtener consejos sobre cómo mejorar el rendimiento, vea [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Compatibilidad Microsoft 365 redes como proveedor de equipos de red

Si es un proveedor de equipos de red, únase al [Programa para partners de redes de Office 365](microsoft-365-networking-partner-program.md). Inscríbase en el programa para compilar principios de conectividad de red de Office 365 en sus productos y soluciones. 

## <a name="office-365-endpoints"></a>Puntos de conexión de Office 365

Los puntos de conexión son el conjunto de direcciones IP de destino, nombres de dominio DNS y URL para el tráfico de Office 365 en Internet. 

Para optimizar el rendimiento de los servicios basados en la nube de Office 365, algunos puntos de conexión necesitan un tratamiento especial por parte de los exploradores cliente y los dispositivos de la red perimetral. Estos dispositivos incluyen firewalls, inspección e interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos.

Vea [Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md) para obtener detalles.

Actualmente, hay cinco nubes diferentes de Office 365. En esta tabla se le indicará la lista de puntos de conexión de cada una.

| Puntos de conexión | Descripción |
|:-------|:-----|
| [Puntos de conexión mundiales](urls-and-ip-address-ranges.md) | Puntos de conexión para suscripciones a Office 365 de todo el mundo, que incluyen Government Community Cloud (GCC) de Estados Unidos. |
| [Puntos de conexión de DoD de Estados Unidos](microsoft-365-u-s-government-dod-endpoints.md) | Puntos de conexión para las suscripciones del Department of Defense (DoD) de Estados Unidos. |
| [Puntos de conexión de GCC High de Estados Unidos](microsoft-365-u-s-government-gcc-high-endpoints.md) | Puntos de conexión para suscripciones a Government Community Cloud High (GCC High) de Estados Unidos. |
| [Puntos de conexión de Office 365 operado por 21Vianet](urls-and-ip-address-ranges-21vianet.md) | Puntos de conexión de Office 365 operado por 21Vianet, que está diseñado para satisfacer las necesidades de Office 365 en China. |
| [Puntos de conexión de Office 365 Germany](microsoft-365-germany-endpoints.md) | Puntos de conexión de una nube independiente en Europa para los clientes con más regulaciones en Alemania, la Unión Europea (UE) y la Asociación Europea de Libre Comercio (AELC). |
|||

Para automatizar la obtención de la lista más reciente de puntos de conexión para su nube de Office 365, vea [Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md).

Para consultar puntos de conexión adicionales, vea estos artículos:

- [Puntos de conexión adicionales no incluidos en el servicio web](additional-office365-ip-addresses-and-urls.md)
- [Solicitudes de red en Office 2016 para Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Temas adicionales para Microsoft 365 redes

Vea estos artículos para obtener temas especializados en Microsoft 365 redes:

- [Redes de entrega de contenido](content-delivery-networks.md)
- [Compatibilidad con IPv6 en servicios de Office 365](ipv6-support.md)
- [Compatibilidad de NAT con Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute para Microsoft 365

Vea estos artículos para obtener información sobre el uso de ExpressRoute para el tráfico de Office 365:

- [Azure ExpressRoute para Office 365](azure-expressroute.md)
- [Implementación de ExpressRoute para Office 365](implementing-expressroute.md)
- [Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)
- [Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)
