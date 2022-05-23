---
title: Microsoft 365 optimización del rendimiento de inquilinos globales para los usuarios de China
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo se proporcionan instrucciones para optimizar el rendimiento de la red para los usuarios de China de inquilinos de Microsoft 365 globales.
ms.openlocfilehash: f7e4e69277a252fd1af52559d3bc4360fd3cfd51
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65637877"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 optimización del rendimiento de inquilinos globales para los usuarios de China

> [!IMPORTANT]
> Esta guía es específica de los escenarios de uso en los que **la empresa Microsoft 365 los usuarios ubicados en China se** conectan a un **inquilino de Microsoft 365 global**. Esta guía **no** se aplica a los inquilinos de Office 365 operados por 21Vianet.

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan Microsoft 365 optimización para usuarios remotos.

>- Para obtener información general sobre el uso de la tunelización dividida de VPN para optimizar la conectividad Microsoft 365 para los usuarios remotos, consulte [Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener instrucciones detalladas sobre la implementación de la tunelización dividida de VPN, consulte [Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md).
>- Para obtener una lista detallada de los escenarios de tunelización dividida de VPN, consulte [Escenarios comunes de tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener instrucciones sobre cómo proteger Teams tráfico multimedia en entornos de tunelización dividida de VPN, consulte [Protección del tráfico multimedia Teams para la tunelización dividida de VPN](microsoft-365-vpn-securing-teams.md).
>- Para obtener información sobre cómo configurar stream y eventos en directo en entornos VPN, consulte [Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md).

Para las empresas con inquilinos de Microsoft 365 globales y una presencia corporativa en China, Microsoft 365 rendimiento del cliente para los usuarios basados en China puede ser complicado por factores únicos de la arquitectura de Internet de China Telco.

Los ISP de China tienen conexiones marítimas reguladas a internet público global que pasan por dispositivos perimetrales que son propensos a altos niveles de congestión de la red transfronteriza. Esta congestión crea pérdida de paquetes y latencia para todo el tráfico de Internet que entra y sale de China.

![Microsoft 365 tráfico: no optimizado.](../media/O365-networking/China-O365-unoptimized.png)

La pérdida y latencia de paquetes son perjudiciales para el rendimiento de los servicios de red, especialmente los servicios que requieren grandes intercambios de datos (como transferencias de archivos grandes) o que requieren un rendimiento casi en tiempo real (aplicaciones de audio y vídeo).

El objetivo de este tema es proporcionar procedimientos recomendados para mitigar el impacto de la congestión de la red transfronteriza de China en Microsoft 365 servicios. En este tema no se abordan otros problemas comunes de rendimiento de última milla, como los problemas de alta latencia de paquetes debido al enrutamiento complejo dentro de los operadores de China.

## <a name="corporate-network-best-practices"></a>Procedimientos recomendados de red corporativa

Muchas empresas con inquilinos y usuarios de Microsoft 365 globales en China han implementado redes privadas que transportan tráfico de red corporativa entre ubicaciones de oficinas de China y ubicaciones extraterritoriales de todo el mundo. Estas empresas pueden aprovechar esta infraestructura de red para evitar la congestión de la red transfronteriza y optimizar el rendimiento del servicio Microsoft 365 en China.

> [!IMPORTANT]
> Al igual que con todas las implementaciones de WAN privadas, siempre debe consultar los requisitos normativos de su país o región para asegurarse de que la configuración de red está en cumplimiento.

Como primer paso, es fundamental que siga nuestra guía de red de pruebas comparativas en [Planeamiento de red y optimización del rendimiento para Microsoft 365](./network-planning-and-performance.md). El objetivo principal debe ser evitar el acceso a los servicios de Microsoft 365 globales desde Internet en China, si es posible.

- Aproveche su red privada existente para llevar el tráfico de red de Microsoft 365 entre las redes de oficinas de China y las ubicaciones offshore que salen en la Red Pública de Internet fuera de China. Casi cualquier ubicación fuera de China proporcionará un beneficio claro. Los administradores de red pueden optimizar aún más la salida en áreas con una interconexión de baja latencia con la [red global de Microsoft](/azure/networking/microsoft-global-network). Hong Kong, Singapur, Japón y Corea del Sur son ejemplos.
- Configure los dispositivos de usuario para acceder a la red corporativa a través de una conexión VPN para permitir que el tráfico de Microsoft 365 transite el vínculo offshore privado de la red corporativa. Asegúrese de que los clientes VPN no estén configurados para usar la tunelización dividida o de que los dispositivos de usuario estén configurados para omitir la tunelización dividida para Microsoft 365 tráfico. Para obtener información adicional sobre cómo optimizar la conectividad VPN para Teams y el tráfico multimedia en tiempo real, consulte [esta sección](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china).
- Configure la red para enrutar todo el tráfico Microsoft 365 a través del vínculo offshore privado. Si debe minimizar el volumen de tráfico en el vínculo privado, puede optar por enrutar solo los puntos de conexión en la categoría **Optimizar** y permitir que las solicitudes a los puntos de conexión **De permiso** y **Predeterminado** transiten Por Internet. Esto mejorará el rendimiento y minimizará el consumo de ancho de banda al limitar el tráfico optimizado a los servicios críticos que son más sensibles a la latencia alta y a la pérdida de paquetes.
- Si es posible, use UDP en lugar de TCP para el tráfico de streaming multimedia en directo, como para Teams. UDP ofrece un mejor rendimiento de streaming multimedia en vivo que TCP.

Para obtener información sobre cómo enrutar de forma selectiva Microsoft 365 tráfico, consulte [Administración de puntos de conexión de Office 365](managing-office-365-endpoints.md). Para obtener una lista de todas las direcciones URL y direcciones IP de Office 365 en todo el mundo, consulte [Office 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md).

![Microsoft 365 tráfico: optimizado.](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Procedimientos recomendados para el usuario

Los usuarios de China que se conectan a inquilinos de Microsoft 365 globales desde ubicaciones remotas como hogares, cafeterías, hoteles y sucursales sin conexión a redes empresariales pueden experimentar un rendimiento de red deficiente porque el tráfico entre sus dispositivos y Microsoft 365 debe transitar los circuitos de red transfronterizo congestionados de China.

Si las redes privadas transfronterizas o el acceso VPN a la red corporativa no son una opción, los problemas de rendimiento por usuario se pueden mitigar entrenando a los usuarios basados en China para que sigan estos procedimientos recomendados.

- Utilice clientes Office enriquecidos que admitan el almacenamiento en caché (por ejemplo, Outlook, Teams, OneDrive, etc.) y evite clientes basados en web. Office el almacenamiento en caché de cliente y las características de acceso sin conexión pueden reducir drásticamente el impacto de la congestión y la latencia de la red.
- Si el inquilino de Microsoft 365 se ha configurado con la característica _de Audioconferencia_, Teams los usuarios pueden unirse a las reuniones a través de la red telefónica conmutada (RTC) pública. Para obtener más información, consulte [Audioconferencia en Office 365](/microsoftteams/audio-conferencing-in-office-365).
- Si los usuarios experimentan problemas de rendimiento de red, deben informar a su departamento de TI para solucionar problemas y escalar al soporte técnico de Microsoft si se sospecha que hay problemas con los servicios de Microsoft 365. No todos los problemas se deben al rendimiento de la red transfronteriza.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Optimización del rendimiento de la red de reuniones Microsoft Teams para los usuarios en China

En el caso de las organizaciones con inquilinos de Microsoft 365 globales y presencia en China, Microsoft 365 rendimiento de cliente para los usuarios basados en China puede ser complicado por factores únicos de la arquitectura de Internet de China. Muchas empresas y escuelas han informado de buenos resultados siguiendo esta guía. Sin embargo, el ámbito se limita a las ubicaciones de red de usuario que están bajo control de la configuración de red de TI, por ejemplo, las ubicaciones de oficina o los puntos de conexión domésticos o móviles con conectividad VPN. Microsoft Teams llamadas y reuniones se usan a menudo desde ubicaciones externas, como oficinas domésticas, ubicaciones móviles, en la carretera y cafeterías. Dado que las llamadas y reuniones se basan en el tráfico multimedia en tiempo real, estas experiencias de Teams son especialmente sensibles a la congestión de la red.

Como resultado, Microsoft se ha asociado con proveedores de telecomunicaciones para llevar Teams y Skype Empresarial tráfico multimedia en tiempo real en línea mediante una ruta de acceso de red preferente y de mayor calidad entre las conexiones a Internet nacionales y públicas en China y los servicios Teams y Skype en la nube global Microsoft 365. Esta funcionalidad ha dado lugar a una mejora de más de diez veces en la pérdida de paquetes y otras métricas clave que afectan a la experiencia del usuario.

>[!IMPORTANT]
>Actualmente, estas mejoras no abordan la asistencia a reuniones de Microsoft Live Events, como grandes reuniones de estilo de difusión o "ayuntamiento" mediante Teams o Microsoft Stream. Las mejoras de red beneficiarán a los usuarios que presentan o producen una reunión de Live Events, ya que esa experiencia actúa como una reunión de Teams regular para el productor o moderador.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Procedimientos recomendados de red de la organización para reuniones Teams

Debe tener en cuenta cómo aprovechar estas mejoras de red, dado que las instrucciones anteriores tienen en cuenta una extensión de red privada para evitar la congestión de la red transfronteriza. Hay dos opciones generales para las redes de office de la organización:

1. No haga nada nuevo. Siga las instrucciones anteriores sobre la omisión de la red privada para evitar la congestión transfronteriza. Teams tráfico multimedia en tiempo real aprovechará esa configuración, como antes.
2. Implemente un patrón dividido o híbrido.
   - Use la guía anterior para todo el tráfico marcado para la optimización, excepto Teams reuniones y llamar al tráfico multimedia en tiempo real.
   - Enrute Teams reunión y llame al tráfico multimedia en tiempo real a través de la red pública de Internet. Consulte la siguiente información para obtener información específica sobre cómo identificar el tráfico de red multimedia en tiempo real.

El envío de Teams tráfico de audio y vídeo multimedia en tiempo real a través de la red pública de Internet, que usa la conectividad de mayor calidad, puede dar lugar a un ahorro considerable de costos, ya que es gratuito frente al pago por enviar ese tráfico a través de una red privada. Puede haber ventajas adicionales similares si los usuarios también usan clientes SDWAN o VPN. Es posible que algunas organizaciones también prefieran tener más datos a través de conexiones públicas a Internet como práctica general.

Las mismas opciones se pueden aplicar a las configuraciones de SDWAN o VPN. Por ejemplo, un usuario usa una VPN o SDWAN para enrutar Microsoft 365 tráfico a la red corporativa y, a continuación, aprovechar la extensión privada de esa red para evitar la congestión transfronteriza. Ahora, sdwan o VPN del usuario se pueden configurar para excluir Teams reunión y llamar al tráfico en tiempo real desde el enrutamiento de VPN. Esta configuración de VPN se conoce como tunelización dividida. Consulte [Túnel dividido de VPN para obtener Office 365](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) para obtener más información.

También puede seguir usando su SDWAN o VPN para todo el tráfico Microsoft 365, incluido para Microsoft Teams tráfico en tiempo real. Microsoft no tiene recomendaciones sobre el uso de soluciones SDWAN o VPN.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Procedimientos recomendados de red principal, móvil y de usuario para reuniones de Teams

Los usuarios de China pueden aprovechar estas mejoras simplemente conectándose al servicio público de Internet en China con una conexión móvil o de teléfono fijo. Teams el tráfico de audio y vídeo multimedia en tiempo real en la red pública de Internet se beneficia directamente de una mejor conectividad y calidad.

Sin embargo, los datos de otros servicios de Microsoft 365(y otro tráfico en Teams, como chats o archivos) no se beneficiarán directamente de estas mejoras. Es posible que los usuarios fuera de la red de la organización sigan experimentando un rendimiento de red deficiente para este tráfico. Como se describe en este artículo, puede mitigar estos efectos mediante una VPN o SDWAN. También puede hacer que los usuarios usen clientes de escritorio enriquecidos a través de clientes web, que admiten el almacenamiento en caché en la aplicación para mitigar los problemas de red.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Identificación de Teams tráfico de red multimedia en tiempo real

Para configurar un dispositivo de red o una configuración de VPN/SDWAN, debe excluir solo el Teams tráfico de audio y vídeo multimedia en tiempo real. Los detalles del tráfico se pueden encontrar para el identificador 11 en la lista oficial de [direcciones URL de Office 365 e intervalos de direcciones IP](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams). Todas las demás configuraciones de red deben permanecer tal cual.

Microsoft trabaja continuamente para mejorar la experiencia del usuario Microsoft 365 y el rendimiento de los clientes en la gama más amplia posible de arquitecturas y características de red. Visite el [Community técnico de redes de Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) para iniciar o unirse a una conversación, buscar recursos y enviar solicitudes y sugerencias de características.

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Implementación de la tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[Escenarios comunes de tunelización dividida de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Protección del tráfico multimedia Teams para la tunelización dividida VPN](microsoft-365-vpn-securing-teams.md)

[Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Microsoft 365 ajuste de red y rendimiento](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
