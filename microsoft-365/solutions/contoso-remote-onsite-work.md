---
title: Respuesta y compatibilidad de COVID-19 de Contoso para el trabajo remoto e in situ
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso Corporation respondió a la pandemia de COVID-19 e ingenió su infraestructura de instalación y actualización de software para el trabajo remoto e in situ.
ms.openlocfilehash: 0bded43f03dd529ffdf463818a93af70e10eed89
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028985"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Respuesta y compatibilidad de COVID-19 de Contoso para el trabajo remoto e in situ

Contoso siempre había admitido a sus trabajadores remotos, que accedieron a los recursos locales a través de un servidor VPN central en la sede central de París. Contoso había emitido a todos los trabajadores remotos un portátil administrado. Los trabajadores locales tenían una mezcla de equipos de escritorio y portátiles.

## <a name="contosos-response-to-covid-19"></a>Respuesta de Contoso a COVID-19

Con el inicio de la pandemia covid-19, de repente todos los trabajadores esenciales eran trabajadores remotos. Contoso respondió cambiando su personal para trabajar desde casa y llevar a cabo sus actividades principales mediante el acceso remoto a recursos locales y en línea mediante servicios en la nube de Microsoft 365.

Contoso tenía servidores VPN de acceso remoto en la oficina central de París para admitir el 25 % de su personal ya remoto, pero rápidamente se movió para ampliar su capacidad de acceso remoto para admitir el 90 % de su personal. Contoso implementó servidores VPN de acceso remoto en cada oficina satélite para que los trabajadores remotos usarían un punto de entrada de cierre regional para obtener acceso a la intranet de Contoso.

Contoso también actualizó la configuración de los clientes VPN instalados en portátiles, tabletas y teléfonos inteligentes para tunelización dividida de modo que el tráfico del conjunto Optimize de puntos de conexión de Office 365 omitió la conexión VPN y se envió directamente a través de Internet. Para obtener más información, vea [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).

Esta es la configuración resultante con dispositivos VPN instalados en la sede central de París y en cada una de las oficinas satélite. 

![Infraestructura VPN de Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Un trabajador remoto con el cliente VPN instalado usa DNS para buscar la oficina regionalmente más cercana y se conecta al dispositivo VPN instalado allí. Con el túnel dividido, el tráfico a los puntos de conexión de Optimización de Microsoft 365 se envía directamente a la ubicación de red de Microsoft 365 más cercana regionalmente. El resto del tráfico se envía a través de la conexión VPN al dispositivo VPN.

## <a name="contosos-support-for-remote-and-onsite-work"></a>Compatibilidad de Contoso con el trabajo remoto e in situ

Después de realizar los cambios iniciales para admitir principalmente trabajadores remotos durante bloqueos regionales, Contoso realizó cambios en la infraestructura para admitir el trabajo remoto e in situ en el que un trabajador podía ser:

- Siempre remoto.
- Siempre en el sitio.
- Una combinación de in situ y remota.

Las características de identidad, seguridad y cumplimiento de Microsoft 365 están diseñadas para que zero trust y funcionen independientemente de la ubicación del usuario y su dispositivo. Para obtener más información, vea [Zero Trust](https://www.microsoft.com/security/business/zero-trust).

Sin embargo, la administración de nuevas instalaciones y actualizaciones de software depende de la ubicación del dispositivo, ya que el software que se va a instalar podría venir de un origen local o de Internet. Los arquitectos de TI de Contoso diseñaron sus nuevas instalaciones y actualiza la infraestructura en función de la ubicación del dispositivo, en lugar del trabajador.

Designaban dos tipos de dispositivos: dedicados localmente e itinerancia.

### <a name="dedicated-on-premises"></a>Dedicado local

Un dispositivo local dedicado es un equipo de escritorio o servidor que nunca sale de la intranet de Contoso y no tiene instalado un cliente VPN. Estos dispositivos locales siguen usando Microsoft Endpoint Configuration Manager y sus puntos de distribución para las instalaciones y actualizaciones de Windows 10, aplicaciones de Microsoft 365 para empresas y el explorador perimetral.

### <a name="roaming"></a>Itinerancia

Un dispositivo móvil puede salir de la intranet de Contoso e incluye portátiles emitidos a muchos trabajadores de oficina y a todos los trabajadores remotos y otros dispositivos propiedad de la organización, como teléfonos inteligentes y tabletas con el cliente VPN de Contoso instalado. 

Dado que estos dispositivos se pueden conectar a Internet en cualquier momento, usan Intune u otros servicios basados en la nube para instalar y actualizar Windows 10, Aplicaciones de Microsoft 365 para empresas y Edge. No usan los puntos de distribución locales de Configuration Manager existentes.

Esto significa que algunas de las instalaciones y actualizaciones del dispositivo móvil se realizarán a través de Internet mientras están locales y conectadas a la intranet. Pero los arquitectos de IT de Contoso decidieron que la simplicidad de la configuración era más importante que la optimización del ancho de banda de intranet a Internet, especialmente cuando la mayoría de los trabajadores remotos rara vez están conectados a la intranet.

Esta es la infraestructura resultante.

![Infraestructura de instalación y actualizaciones de Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

El comportamiento de instalación y actualización se determina al convertir las cuentas de equipo de los dispositivos en miembros de uno de estos grupos:

- OnPremDevices

  El cliente de Configuration Manager en el dispositivo usa puntos de distribución para las descargas y actualizaciones.

- RoamingDevices

  Intune y otras opciones de configuración del dispositivo especifican el uso de la red de Microsoft 365 para instalar y actualizar.

## <a name="new-onboarding-process"></a>Nuevo proceso de incorporación

Para un nuevo dispositivo local dedicado emitido a un nuevo trabajador o a un nuevo servidor en un centro de datos, cuando el trabajador inicia sesión, el cliente de Configuration Manager basado en la pertenencia del dispositivo al grupo OnPremDevices descarga e instala las actualizaciones más recientes para Windows 10, Aplicaciones de Microsoft 365 para empresas y Edge desde puntos de distribución locales de Configuration Manager. Cuando se completa, el dispositivo local dedicado está listo para su uso y usa estos puntos de distribución para actualizaciones continuas.

Para un nuevo dispositivo remoto emitido a un nuevo trabajador, cuando el trabajador inicia sesión, el dispositivo, según su pertenencia al grupo RoamingDevices, se pone en contacto con el servicio en la nube de Intune y otros servicios y descarga e instala las actualizaciones más recientes para Windows 10, Aplicaciones de Microsoft 365 para empresas y Edge. Una vez completado, el dispositivo remoto está listo para su uso y usa el cliente VPN instalado para obtener acceso a los recursos locales y a la red de Microsoft 365 para actualizaciones continuas.

## <a name="next-step"></a>Paso siguiente

[Faculta a los trabajadores remotos](empower-people-to-work-remotely.md) de la organización.
