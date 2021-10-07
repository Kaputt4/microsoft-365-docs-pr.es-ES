---
title: Microsoft 365 Óptica de conectividad
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: Este artículo contiene información sobre Microsoft 365 óptica de conectividad.
ms.openlocfilehash: c1ee14966f13ff50ff809ebbdf4c578bf949e956
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150550"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365 Óptica de conectividad

En este documento se describen algunas de las ópticas de conectividad que Microsoft suele recopilar de los dispositivos del cliente y se describen algunas de las formas en que Microsoft usa estos datos para analizar y optimizar la entrega del servicio y para evaluar y garantizar la mejor experiencia posible para el usuario final.

Por lo general, la óptica de conectividad se recopila desde aplicaciones de Microsoft, que pueden instalarse en dispositivos de usuario final o tener acceso desde exploradores. A diferencia de la recopilación de datos opcional dentro de Microsoft 365 servicios, muchas de las ópticas de conectividad descritas aquí son integrales para garantizar que Microsoft cumpla con nuestro compromiso de disponibilidad y rendimiento con los clientes. Estas ópticas permiten a Microsoft detectar y responder rápidamente a cualquier problema en la ruta de conectividad entre los usuarios finales y los puntos de conexión de servicio de Microsoft. Algunas de estas ópticas también se usan para habilitar características como la conectividad de [red en el centro de Administración de Microsoft 365 .](office-365-network-mac-perf-overview.md)

## <a name="optics-collected-from-microsoft-365-applications"></a>Ópticas recopiladas de Microsoft 365 aplicaciones

Actualmente, las ópticas se recopilan con muestreo poco frecuente en todos los dispositivos. En general, Microsoft configura el conjunto específico de ópticas y destinos (puntos de conexión de servicio) que se van a medir en una iteración determinada según los requisitos de servicio y se aleatorizan para fines de muestreo.
En cada intervalo de recopilación de óptica, se pueden recopilar una o más de las siguientes medidas usando el dispositivo del usuario final como origen de medida y un punto de conexión de servicio Microsoft 365 como destino de medida:

| Medida | Descripción |
| --- | --- |
| Latencia | Tiempo que se necesita para recuperar un archivo pequeño a través de HTTP |
| Rendimiento | Tiempo necesario para recuperar un archivo más grande a través de HTTP, medido en raras ocasiones para evitar un consumo excesivo de ancho de banda |
| Hora de ida y vuelta (RTT) | Ping ICMP |
| Traceroute | Traceroute ICMP |

Cada medida suele estar asociada con información adicional, que puede incluir los siguientes elementos:

| Elemento | Descripción |
| --- | --- |
| Identificación del inquilino | Identificador único para el espacio empresarial del Azure Active Directory asociado con el dispositivo del usuario final. |
| Id. de monitor | Identificador de la aplicación que genera la solicitud (como Outlook, OneDrive, etc.), proporcionado por la aplicación cliente que realiza la medida. |
| ID de solicitud | Identificador de la solicitud de medida, especificada en la configuración de medida proporcionada por Microsoft. |
| IP remota | IP de origen enmascarada asociada con la solicitud de extremo de cliente a servicio, proporcionada por el servidor que recibió la solicitud de medida y calculada en función de la dirección IP de origen del cliente que microsoft puede ver. Las direcciones IP se enmascaran en una subred /24 para direcciones IPv4 o una subred /48 para direcciones IPv6 para garantizar que Microsoft no puede identificar dispositivos o usuarios individuales. |
| Front-end | Microsoft 365 de servicio front-end proporcionado por el servidor que recibió la solicitud de medida. |
| Punto de conexión | Microsoft 365 punto de conexión de servicio proporcionado por el servidor que recibió la solicitud de medida. |
| Certificado emitido por | La propiedad "certificado emitido por" del certificado SSL presentado al conectarse al extremo de servicio, que indica la entidad de certificación que emitió el certificado al extremo de servicio. |
| Huella digital del certificado | La propiedad "huella digital del certificado" del certificado SSL presentada al conectarse al punto de conexión de servicio, que es un identificador único accesible públicamente del certificado. |
| Latitud/longitud | Latitud y longitud abstractas del dispositivo del usuario final. Esto solo se recopila para los inquilinos que han habilitado Windows Servicio de ubicación en dispositivos de usuario final y también han habilitado la recopilación de esta información en el portal de administración de [Microsoft 365.](office-365-network-mac-perf-overview.md#1-enable-windows-location-services) |

## <a name="measurement-process"></a>Proceso de medición

Cada dispositivo de usuario final suele realizar una medición de forma programada (para aplicaciones instaladas) o en función de la acción de cargar páginas del explorador (para aplicaciones basadas en web). Las actividades de medición se realizan como operaciones en segundo plano y no afectan a la experiencia de la aplicación para los usuarios. A medida que se aleatorizan los tipos de medida y los destinos que se usarán para una iteración determinada de este proceso, los clientes pueden observar solicitudes a puntos de conexión de servicio de Microsoft en su región que son similares a las solicitudes típicas realizadas por dispositivos de usuario final para la conectividad normal de aplicaciones. Además, es posible que los clientes noten solicitudes a puntos de conexión de servicio de Microsoft que se encuentran fuera de su región local. Estas medidas se usan a menudo para garantizar un enrutamiento óptimo de las solicitudes de cliente al mejor punto de conexión de servicio, ya que los cambios en la infraestructura de cliente e ISP pueden requerir que Microsoft cambie nuestras directivas de enrutamiento de solicitudes de forma continua. Obtenga más información sobre cómo Microsoft enruta el tráfico al mejor punto de conexión de servicio y cómo optimizar la conectividad a Microsoft 365 servicios en el Microsoft 365 de conectividad [de red.](microsoft-365-networking-overview.md)

## <a name="service-endpoints"></a>Puntos de conexión de servicios

Los puntos de conexión de servicio de Microsoft que se usan como destinos para estas medidas se encuentran dentro de las direcciones URL y los intervalos de direcciones [IP publicados Office 365.](urls-and-ip-address-ranges.md) El acceso a puntos de conexión de servicio adicionales no es necesario para la recopilación de estas ópticas de conectividad.
