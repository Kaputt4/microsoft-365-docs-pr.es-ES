---
title: Optimización del rendimiento global de inquilinos de Microsoft 365 para usuarios de China
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo se proporcionan instrucciones para optimizar el rendimiento de la red para los usuarios de China de inquilinos globales de Microsoft 365.
ms.openlocfilehash: 9b397e60b4a3b80563ed31731a6f7aa8e0bdab7f
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456368"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Optimización del rendimiento global de inquilinos de Microsoft 365 para usuarios de China

>[!IMPORTANT]
>Esta guía es específica para escenarios de uso en los que los usuarios empresariales de **Microsoft 365** ubicados en China se conectan a un inquilino global de **Microsoft 365.** Esta guía no **se aplica** a los inquilinos de Office 365 operado por 21Vianet.

Para las empresas con inquilinos globales de Microsoft 365 y una presencia corporativa en China, el rendimiento del cliente de Microsoft 365 para los usuarios basados en China puede ser complicado por factores exclusivos de la arquitectura de Internet de China Telino.

Los ISP de China tienen conexiones reguladas conexiones a Internet pública global que pasan por dispositivos perimetrales propensos a altos niveles de congestión de la red entre fronteras. Esta congestión crea pérdida de paquetes y latencia para todo el tráfico de Internet que entra y sale de China.

![Tráfico de Microsoft 365: sin optimizar](../media/O365-networking/China-O365-unoptimized.png)

La pérdida de paquetes y la latencia son perjudiciales para el rendimiento de los servicios de red, especialmente los servicios que requieren grandes intercambios de datos (como transferencias de archivos grandes) o que requieren un rendimiento casi en tiempo real (aplicaciones de audio y vídeo).

El objetivo de este tema es proporcionar procedimientos recomendados para mitigar el impacto de la congestión de la red entre fronteras de China en los servicios de Microsoft 365. En este tema no se abordan otros problemas comunes de rendimiento de última milla, como los problemas de latencia alta de paquetes debido al enrutamiento complejo dentro de los operadores de China.

## <a name="corporate-network-best-practices"></a>Procedimientos recomendados de red corporativa

Muchas empresas con inquilinos globales de Microsoft 365 y usuarios en China han implementado redes privadas que transportan tráfico de red corporativa entre ubicaciones de oficinas de China y ubicaciones de sucursales en todo el mundo. Estas empresas pueden aprovechar esta infraestructura de red para evitar la congestión de la red entre fronteras y optimizar el rendimiento del servicio de Microsoft 365 en China.

>[!IMPORTANT]
>Al igual que con todas las implementaciones de WAN privadas, siempre debe consultar los requisitos normativos de su país o región para asegurarse de que la configuración de red está en cumplimiento.

Como primer paso, es fundamental que siga nuestras directrices de red comparativas sobre planeación de red y ajuste del rendimiento [de Microsoft 365.](https://aka.ms/tune) El objetivo principal debe ser evitar el acceso a los servicios globales de Microsoft 365 desde Internet en China si es posible.

- Aproveche su red privada existente para transportar el tráfico de red de Microsoft 365 entre las redes de oficina de China y las ubicaciones de las sucursales que salir de Internet pública fuera de China. Casi cualquier ubicación fuera de China proporcionará una ventaja clara. Los administradores de red pueden optimizar aún más mediante la salida en áreas con interconexión de baja latencia con la [red global de Microsoft.](https://docs.microsoft.com/azure/networking/microsoft-global-network) Hong Kong, Japón y Corea del Sur son ejemplos.
- Configurar los dispositivos de usuario para que accedan a la red corporativa a través de una conexión VPN para permitir que el tráfico de Microsoft 365 transite el vínculo de enlace privado de la red corporativa. Asegúrese de que los clientes VPN no estén configurados para usar túnel dividido o que los dispositivos de usuario estén configurados para omitir el túnel dividido para el tráfico de Microsoft 365.
- Configure su red para enrutar todo el tráfico de Microsoft 365 a través de su vínculo privado de la plataforma móvil. Si debe minimizar el volumen de tráfico en el vínculo privado, puede elegir enrutar  solo  los puntos de conexión en la categoría Optimizar y permitir que las solicitudes a los puntos de conexión permitir y predeterminados transiten por Internet.  Esto mejorará el rendimiento y minimizará el consumo de ancho de banda limitando el tráfico optimizado a los servicios críticos que son más sensibles a la latencia alta y la pérdida de paquetes.
- Si es posible, use UDP en lugar de TCP para el tráfico de streaming de medios en directo, como para Teams. UDP ofrece un mejor rendimiento de streaming de medios en directo que TCP.

Para obtener información sobre cómo enrutar el tráfico de Microsoft 365 de forma selectiva, vea Administrar puntos de conexión [de Office 365.](managing-office-365-endpoints.md) Para obtener una lista de todas las direcciones IP y DIRECCIONES URL de Office 365 en todo el mundo, vea direcciones URL e intervalos de direcciones IP de [Office 365.](urls-and-ip-address-ranges.md)

![Tráfico de Microsoft 365: optimizado](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedimientos recomendados de usuario

Los usuarios de China que se conectan a inquilinos globales de Microsoft 365 desde ubicaciones remotas como hogar, cafeterías, restaurantes y sucursales sin conexión a redes empresariales pueden experimentar un rendimiento de red deficiente, ya que el tráfico entre sus dispositivos y Microsoft 365 debe transitar por los circuitos de red entre fronteras congestionados de China.

Si las redes privadas cruzadas o el acceso VPN a la red corporativa no son una opción, los problemas de rendimiento por usuario aún se pueden mitigar al formar a los usuarios basados en China para que sigan estos procedimientos recomendados.

- Use clientes enriquecidos de Office que admitan el almacenamiento en caché (por ejemplo, Outlook, Teams, OneDrive, etc.) y evite clientes basados en web. Las características de almacenamiento en caché de clientes de Office y acceso sin conexión pueden reducir considerablemente el impacto de la congestión y la latencia de la red.
- Si su inquilino de Microsoft 365 se ha configurado con la característica _audioconferencia,_ los usuarios de Teams pueden unirse a reuniones a través de la red telefónica conmutada (RTC). Para obtener más información, [vea Audioconferencia en Office 365.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)
- Si los usuarios experimentan problemas de rendimiento de la red, deben informar a su departamento de TI para solucionar problemas y remitirse al soporte técnico de Microsoft si se sospecha que hay problemas con los servicios de Microsoft 365. No todos los problemas se origina en el rendimiento de la red entre borde.

Microsoft está trabajando continuamente para mejorar la experiencia del usuario de Microsoft 365 y el rendimiento de los clientes en la gama más amplia posible de arquitecturas y características de red. Visite la [comunidad técnica de Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) para iniciar o unirse a una conversación, buscar recursos y enviar sugerencias y solicitudes de características.

## <a name="related-topics"></a>Temas relacionados

[Planeamiento de red y ajuste del rendimiento para Microsoft 365](https://aka.ms/tune)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Red global de Microsoft](https://docs.microsoft.com/azure/networking/microsoft-global-network)
