---
title: Microsoft 365 Introducción a la conectividad de red
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Explica por qué la optimización de red es importante para los servicios SaaS, el objetivo de Microsoft 365 redes y cómo SaaS requiere redes diferentes de otras cargas de trabajo.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923187"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Información general de conectividad de red de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 es una nube de software como servicio (SaaS) distribuida que proporciona escenarios de productividad y colaboración a través de un conjunto diverso de microservicios y aplicaciones. Los componentes de cliente de Microsoft 365 como Outlook, Word y PowerPoint se ejecutan en equipos de usuario y se conectan a otros componentes de Microsoft 365 que se ejecutan en centros de datos de Microsoft. El factor más significativo que determina la calidad de la experiencia del usuario final de Microsoft 365 es la confiabilidad de la red y la baja latencia entre clientes de Microsoft 365 y puertas Microsoft 365 de servicio.

En este artículo, aprenderá sobre los objetivos de las redes Microsoft 365 y por qué Microsoft 365 red requiere un enfoque diferente a la optimización que el tráfico genérico de Internet.

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 de red

El objetivo final de Microsoft 365 red es optimizar la experiencia del usuario final habilitando el acceso menos restrictivo entre los clientes y los puntos de conexión Microsoft 365 más cercanos. La calidad de la experiencia del usuario final está directamente relacionada con el rendimiento y la capacidad de respuesta de la aplicación que usa el usuario. Por ejemplo, Microsoft Teams se basa en una latencia baja para que las llamadas telefónicas de usuario, las conferencias y las colaboraciones de pantalla compartida no tienen problemas y Outlook se basa en una gran conectividad de red para características de búsqueda instantánea que aprovechan las capacidades de indexación y AI del lado servidor.

El objetivo principal del diseño de red debe ser minimizar la latencia reduciendo el tiempo de ida y vuelta (RTT) de los equipos cliente a la Red global de Microsoft, la red troncal pública de Microsoft que interconecta todos los centros de datos de Microsoft con puntos de entrada de aplicaciones en la nube de baja latencia y alta disponibilidad repartidos por todo el mundo. Puede obtener más información sobre la Red Global de Microsoft en [Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

La optimización Microsoft 365 rendimiento de red no tiene que ser complicado. Puede obtener el mejor rendimiento posible siguiendo algunos principios clave:

- Identificar Microsoft 365 tráfico de red
- Permitir la salida de sucursales locales Microsoft 365 tráfico de red a Internet desde cada ubicación en la que los usuarios se conectan a Microsoft 365
- Permitir Microsoft 365 tráfico para omitir servidores proxy y dispositivos de inspección de paquetes

Para obtener más información Microsoft 365 principios de conectividad de red, [vea Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Arquitecturas de red tradicionales y SaaS

Los principios de arquitectura de red tradicionales para cargas de trabajo de cliente y servidor están diseñados en torno a la suposición de que el tráfico entre clientes y extremos no se extiende fuera del perímetro de red corporativa. Además, en muchas redes empresariales, todas las conexiones salientes de Internet atraviesan la red corporativa y la salida desde una ubicación central.

En las arquitecturas de red tradicionales, una mayor latencia para el tráfico genérico de Internet es un equilibrio necesario para mantener la seguridad perimetral de la red, y la optimización del rendimiento para el tráfico de Internet normalmente implica actualizar o escalar horizontalmente el equipamiento en puntos de salida de red. Sin embargo, este enfoque no aborda los requisitos para un rendimiento de red óptimo de los servicios SaaS, como Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identificación Microsoft 365 tráfico de red

Estamos facilitando la identificación de Microsoft 365 de red y facilitando la administración de la identificación de red.

- Nuevas categorías de extremos de red para diferenciar el tráfico de red muy crítico del tráfico de red, que no se ve afectado por las latencias de Internet. Solo hay un puñado de direcciones URL y direcciones IP compatibles en la categoría más crítica "Optimizar".
- Servicios web para el uso de scripts o la configuración directa de dispositivos y la administración de cambios Microsoft 365 identificación de red. Los cambios están disponibles desde el servicio web, o en formato RSS, o en el correo electrónico mediante una Microsoft Flow plantilla.
- [Office 365 de partners de](./microsoft-365-networking-partner-program.md) red con partners de Microsoft que proporcionan dispositivos o servicios que siguen Microsoft 365 principios de conectividad de red y tienen una configuración sencilla.

## <a name="securing-microsoft-365-connections"></a>Proteger Microsoft 365 conexiones

El objetivo de la seguridad de red tradicional es fortalecer el perímetro de la red corporativa frente a vulnerabilidades de seguridad malintencionadas e intrusiones. La mayoría de las redes empresariales aplican la seguridad de red para el tráfico de Internet mediante tecnologías como servidores proxy, firewalls, interrupción e inspección de SSL, inspección de paquetes profunda y sistemas de prevención de pérdida de datos. Estas tecnologías proporcionan una importante mitigación de riesgos para las solicitudes de Internet genéricas, pero pueden reducir drásticamente el rendimiento, la escalabilidad y la calidad de la experiencia del usuario final cuando se aplican a los puntos de conexión de Microsoft 365.

Microsoft 365 ayuda a satisfacer las necesidades de la organización para la seguridad del contenido y el cumplimiento del uso de datos con características de seguridad y gobierno integradas diseñadas específicamente para Microsoft 365 características y cargas de trabajo. Para obtener más información sobre Microsoft 365 seguridad y cumplimiento normativo, vea el mapa de [ruta Office 365 seguridad.](/office365/securitycompliance/security-roadmap) Para obtener más información acerca de las recomendaciones y la posición de soporte técnico de Microsoft en soluciones de red avanzadas que realizan procesamiento de nivel avanzado en el tráfico de Microsoft 365, vea [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>¿Por qué Microsoft 365 redes es diferente?

Microsoft 365 está diseñado para un rendimiento óptimo mediante la seguridad de puntos de conexión y las conexiones de red cifradas, lo que reduce la necesidad de aplicación de seguridad perimetral. Microsoft 365 centros de datos están ubicados en todo el mundo y el servicio está diseñado para usar varios métodos para conectar clientes a los mejores puntos de conexión de servicio disponibles. Dado que los datos y el procesamiento del usuario se distribuyen entre muchos centros de datos de Microsoft, no hay ningún extremo de red único al que puedan conectarse los equipos cliente. De hecho, los datos y servicios de su inquilino de Microsoft 365 están optimizados dinámicamente por Microsoft Global Network para adaptarse a las ubicaciones geográficas desde las que tienen acceso los usuarios finales.

Algunos problemas comunes de rendimiento se crean cuando Microsoft 365 tráfico está sujeto a la inspección de paquetes y a la salida centralizada:

- Una latencia alta puede provocar un rendimiento extremadamente bajo de las secuencias de vídeo y audio, y una respuesta lenta de recuperación de datos, búsquedas, colaboración en tiempo real, información de disponibilidad de calendario, contenido del producto y otros servicios
- Las conexiones de salida desde una ubicación central vencen las capacidades de enrutamiento dinámico de la red global Microsoft 365, lo que agrega latencia y tiempo de ida y vuelta
- Descifrar SSL protegido Microsoft 365 tráfico de red y volver a cifrarlo puede provocar errores de protocolo y tiene riesgo de seguridad

Acortar la ruta de acceso de red Microsoft 365 los puntos de entrada al permitir que el tráfico del cliente se cierre lo más cerca posible de su ubicación geográfica puede mejorar el rendimiento de conectividad y la experiencia del usuario final en Microsoft 365. También puede ayudar a reducir el impacto de futuros cambios en la arquitectura de red en Microsoft 365 rendimiento y confiabilidad. El modelo de conectividad óptimo es proporcionar siempre salida de red en la ubicación del usuario, independientemente de si se encuentra en la red corporativa o en ubicaciones remotas como hogar, hoteles, cafeterías y aeropuertos. El tráfico genérico de Internet y el tráfico de red corporativa basado en WAN se enrutaría por separado y no usaría el modelo de salida directa local. El siguiente diagrama representa este modelo de salida directa local.

![Arquitectura de red de salida local](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

La arquitectura de salida local presenta las siguientes ventajas para el tráfico de red de Microsoft 365 respecto al modelo tradicional:
  
- Ofrece rendimiento óptimo de Microsoft 365 al optimizar la longitud de la ruta. Las conexiones de usuario final se enrutan dinámicamente al punto  de entrada de Microsoft 365 más cercano mediante la infraestructura de puerta principal del servicio distribuido de la Red global de Microsoft y, a continuación, el tráfico se enruta internamente a los puntos de conexión de servicio y datos a través de la fibra de alta disponibilidad de latencia ultra baja de Microsoft.
- Reduce la carga en la infraestructura de red corporativa al permitir la salida local para el tráfico Microsoft 365, el desvío de servidores proxy y dispositivos de inspección de tráfico.
- Protege las conexiones en ambos extremos aprovechando las características de seguridad de extremo de cliente y de seguridad en la nube, evitando la aplicación de tecnologías de seguridad de red redundantes.

> [!NOTE]
> La _infraestructura de puerta principal del_ servicio distribuido es el perímetro de red escalable y altamente disponible de Microsoft Global Network con ubicaciones distribuidas geográficamente. Finaliza las conexiones de usuario final y las enruta de forma eficaz dentro de la red global de Microsoft. Puede obtener más información sobre la Red Global de Microsoft en [Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Para obtener más información sobre cómo comprender y aplicar Microsoft 365 principios de conectividad de red, [vea Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Conclusión

La optimización Microsoft 365 rendimiento de red realmente se debe a la eliminación de impedimentos innecesarios. Al tratar las Microsoft 365 como tráfico de confianza, puede evitar que la latencia se introduzca mediante la inspección de paquetes y la competencia para el ancho de banda de proxy. Permitir conexiones locales entre máquinas cliente y puntos de conexión Office 365 permite que el tráfico se enruta dinámicamente a través de la red global de Microsoft.

## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Planeamiento de red y ajuste del rendimiento para Microsoft 365](network-planning-and-performance.md)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)

[Redes de entrega de contenido](content-delivery-networks.md)

[Prueba de conectividad de Microsoft 365](https://aka.ms/netonboard)

[Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)