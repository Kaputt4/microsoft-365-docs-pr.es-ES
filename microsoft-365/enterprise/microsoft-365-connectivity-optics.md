---
title: Óptica de conectividad Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Este artículo contiene información sobre la conectividad óptica de Microsoft 365.
ms.openlocfilehash: cda5fa074aa04be5fbbaff9b98360a3a2f927fc2
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090327"
---
# <a name="microsoft-365-connectivity-optics"></a>Óptica de conectividad Microsoft 365

En este documento se describen algunas de las ópticas de conectividad que Microsoft suele recopilar de los dispositivos del cliente y se describen algunas de las formas en que Microsoft usa estos datos para analizar y optimizar la entrega del servicio y evaluar y garantizar la mejor experiencia posible del usuario final.

Por lo general, las ópticas de conectividad se recopilan de las aplicaciones de Microsoft, que pueden instalarse en dispositivos de usuario final o acceder a ellas desde exploradores. A diferencia de la recopilación de datos opcional dentro de Microsoft 365 servicios, muchas de las ópticas de conectividad descritas aquí son fundamentales para garantizar que Microsoft cumple con nuestro compromiso de disponibilidad y rendimiento con los clientes. Estas ópticas permiten a Microsoft detectar y responder rápidamente a cualquier problema en la ruta de conectividad entre los usuarios finales y los puntos de conexión de servicio de Microsoft. Algunas de estas ópticas también se usan para habilitar características como [la conectividad de red en el Centro de Administración de Microsoft 365](office-365-network-mac-perf-overview.md).

## <a name="optics-collected-from-microsoft-365-applications"></a>Óptica recopilada de aplicaciones Microsoft 365

Actualmente, las ópticas se recopilan mediante muestreos poco frecuentes en todos los dispositivos. Como cuestión general, Microsoft configura el conjunto específico de ópticas y destinos (puntos de conexión de servicio) que se van a medir en una iteración determinada en función de los requisitos del servicio y se aleatorizan con fines de muestreo.
En cada intervalo de recopilación de óptica, se pueden recopilar una o varias de las medidas siguientes mediante el dispositivo del usuario final como origen de medición y un punto de conexión de servicio Microsoft 365 como destino de medición:

| Medición | Descripción |
| --- | --- |
| Latencia | Tiempo necesario para recuperar un archivo pequeño a través de HTTP |
| Rendimiento | Tiempo necesario para recuperar un archivo más grande a través de HTTP, medido rara vez para evitar un consumo excesivo de ancho de banda |
| Tiempo de ida y vuelta (RTT) | Ping ICMP |
| Traceroute | Ruta de seguimiento ICMP |

Cada medida suele asociarse con información adicional, que puede incluir los siguientes elementos:

| Elemento | Descripción |
| --- | --- |
| Identificación del inquilino | Identificador único del inquilino de Azure Active Directory del cliente asociado al dispositivo del usuario final. |
| Id. de supervisión | Identificador de la aplicación que genera la solicitud (por ejemplo, Outlook, OneDrive, etc.), proporcionada por la aplicación cliente que realiza la medición. |
| ID de solicitud | Identificador de la solicitud de medida, especificada en la configuración de medida proporcionada por Microsoft. |
| IP remota | Dirección IP de origen enmascarada asociada a la solicitud del punto de conexión de cliente a servicio, proporcionada por el servidor que recibió la solicitud de medida y calculada en función de la dirección IP de origen del cliente que es visible para Microsoft. Las direcciones IP se enmascaran en una subred /24 para direcciones IPv4 o en una subred /48 para direcciones IPv6 para asegurarse de que Microsoft no puede identificar dispositivos o usuarios individuales. |
| Front-end | Microsoft 365 identificador de front-end del servicio, proporcionado por el servidor que recibió la solicitud de medida. |
| Punto de conexión | Microsoft 365 ubicación del punto de conexión de servicio, proporcionada por el servidor que recibió la solicitud de medida. |
| Certificado emitido por | La propiedad "certificado emitido por" del certificado SSL presentado al conectarse al punto de conexión de servicio, que indica la entidad de certificación que emitió el certificado al punto de conexión de servicio. |
| Huella digital del certificado | La propiedad "huella digital del certificado" del certificado SSL presentada al conectarse al punto de conexión de servicio, que es un identificador único accesible públicamente del certificado. |
| Latitud/longitud | Latitud y longitud abstractas del dispositivo del usuario final. Esto solo se recopila para los inquilinos que han habilitado Windows Location Service en dispositivos de usuario final y que también han [habilitado la recopilación de esta información en el portal de administración de Microsoft 365](office-365-network-mac-perf-overview.md#1-enable-windows-location-services). |

## <a name="measurement-process"></a>Proceso de medición

Cada dispositivo de usuario final normalmente realizará una medición de forma programada (para aplicaciones instaladas) o en función de la acción de cargar páginas del explorador (para aplicaciones basadas en web). Las actividades de medición se realizan como operaciones en segundo plano y no afectan a la experiencia de la aplicación para los usuarios. A medida que los tipos de medida y los destinos que se usarán para una iteración determinada de este proceso son aleatorios, los clientes pueden observar solicitudes a puntos de conexión de servicio de Microsoft en su región que son similares a las solicitudes típicas realizadas por los dispositivos de usuario final para la conectividad normal de aplicaciones. Además, los clientes pueden observar solicitudes a puntos de conexión de servicio de Microsoft que están fuera de su región local. Estas medidas se usan a menudo para garantizar un enrutamiento óptimo de las solicitudes de los clientes al mejor punto de conexión de servicio, ya que los cambios en la infraestructura del cliente y el ISP pueden requerir que Microsoft cambie nuestras directivas de enrutamiento de solicitudes de forma continuada. Obtenga más información sobre cómo Microsoft enruta el tráfico al mejor punto de conexión de servicio y cómo optimizar la conectividad con los servicios de Microsoft 365 en la [introducción a la conectividad de red Microsoft 365](microsoft-365-networking-overview.md).

## <a name="service-endpoints"></a>Puntos de conexión de servicios

Los puntos de conexión de servicio de Microsoft que se usan como destinos para estas medidas se encuentran dentro de las [direcciones URL de Office 365 publicadas y los intervalos de direcciones IP](urls-and-ip-address-ranges.md). El acceso a puntos de conexión de servicio adicionales no es necesario para la recopilación de estas ópticas de conectividad.
