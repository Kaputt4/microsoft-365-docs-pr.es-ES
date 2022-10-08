---
title: Respuesta de COVID-19 de Contoso y compatibilidad con el trabajo híbrido
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo contoso Corporation respondió a la pandemia de COVID-19 y diseñó su infraestructura de instalación y actualización de software para el trabajo híbrido.
ms.openlocfilehash: f59017c8da65317233d13b3fa2b5d0c0d234af68
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67987156"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Respuesta de COVID-19 de Contoso y compatibilidad con el trabajo híbrido

Contoso siempre ha apoyado a sus trabajadores remotos, que acceden a los recursos locales a través de un servidor VPN central en la sede central de París. Contoso había emitido a todos los trabajadores remotos un portátil administrado. Los trabajadores locales tenían una mezcla de equipos de escritorio y portátiles.

## <a name="contosos-response-to-covid-19"></a>Respuesta de Contoso a COVID-19

Con el inicio de la pandemia del COVID-19, de repente todos los trabajadores esenciales eran trabajadores remotos. Contoso respondió cambiando su personal para trabajar desde casa y llevar a cabo sus actividades principales a través del acceso remoto a los recursos locales y en línea mediante los servicios en la nube de Microsoft 365.

Contoso tenía servidores VPN de acceso remoto en la oficina central de París para dar soporte al 25 % de su personal ya remoto, pero rápidamente se movió para escalar verticalmente su capacidad de acceso remoto para dar soporte al 90 % de su personal. Contoso implementó servidores VPN de acceso remoto en cada oficina satélite para que los trabajadores remotos usaran un punto de entrada de cierre regional para el acceso a la intranet de Contoso.

Contoso también actualizó la configuración de los clientes VPN instalados en portátiles, tabletas y teléfonos inteligentes para la tunelización dividida, de modo que el tráfico del conjunto optimize de puntos de conexión de Office 365 omitió la conexión VPN y se envió directamente a través de Internet. Para obtener más información, consulte [Optimización de la conectividad Office 365 para usuarios remotos mediante la tunelización dividida de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

Esta es la configuración resultante con dispositivos VPN instalados en la sede central de París y en cada una de las oficinas satélite. 

![Infraestructura de VPN de Contoso.](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Un trabajo remoto con el cliente VPN instalado usa DNS para buscar la oficina regionalmente más cercana y se conecta al dispositivo VPN instalado allí. Con la tunelización dividida, el tráfico a los puntos de conexión de Microsoft 365 Optimize se envía directamente a la ubicación de red de Microsoft 365 más cercana a la región. El resto del tráfico se envía a través de la conexión VPN al dispositivo VPN.

## <a name="contosos-support-for-hybrid-work"></a>Compatibilidad de Contoso con el trabajo híbrido

Después de realizar los cambios iniciales para admitir principalmente a los trabajadores remotos durante los bloqueos regionales, Contoso realizó cambios en la infraestructura para admitir el trabajo híbrido en el que un trabajador podría ser:

- Siempre remoto.
- Siempre en el sitio.
- Una combinación de in situ y remoto.

Las características de identidad, seguridad y cumplimiento de Microsoft 365 están diseñadas para Confianza cero y para funcionar independientemente de la ubicación del usuario y su dispositivo. Para obtener más información, consulte [Confianza cero](https://www.microsoft.com/security/business/zero-trust).

Sin embargo, la administración de nuevas instalaciones y actualizaciones de software depende de la ubicación del dispositivo, ya que el software que se va a instalar podría proceder de un origen local o de Internet. Los arquitectos de TI de Contoso diseñaron sus nuevas instalaciones y actualizaciones de la infraestructura en función de la ubicación del dispositivo, en lugar del trabajo.

Designaron dos tipos de dispositivos: dedicados en el entorno local y en itinerancia.

### <a name="dedicated-on-premises"></a>Dedicado localmente

Un dispositivo local dedicado es un equipo de escritorio o servidor que nunca sale de la intranet de Contoso y no tiene instalado un cliente VPN. Estos dispositivos locales siguen usando microsoft endpoint Configuration Manager y sus puntos de distribución para instalar y actualizar Windows 10, Aplicaciones Microsoft 365 para empresas y el explorador Edge.

### <a name="roaming"></a>Roaming

Un dispositivo móvil puede salir de la intranet de Contoso e incluye equipos portátiles emitidos a muchos trabajadores de la oficina y a todos los trabajadores remotos y otros dispositivos propiedad de la organización, como teléfonos inteligentes y tabletas con el cliente VPN de Contoso instalado. 

Dado que estos dispositivos se pueden conectar a Internet en un momento dado, usan Intune u otros servicios basados en la nube para instalar y actualizar Windows 10, Aplicaciones Microsoft 365 para empresas y Edge. No usan los puntos de distribución locales existentes Configuration Manager.

Esto significa que algunas de las instalaciones y actualizaciones del dispositivo móvil se realizarán a través de Internet mientras estén locales y conectadas a la intranet. Pero los arquitectos de TI de Contoso decidieron que la simplicidad de la configuración era más importante que la optimización del ancho de banda de intranet a Internet, especialmente cuando la mayoría de los trabajadores remotos rara vez están conectados a la intranet.

Esta es la infraestructura resultante.

![La infraestructura de instalación y actualizaciones de Contoso.](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

El comportamiento de instalación y actualización se determina haciendo que las cuentas de equipo de los dispositivos sean miembros de uno de estos grupos:

- OnPremDevices

  El cliente Configuration Manager del dispositivo usa puntos de distribución para las instalaciones y actualizaciones.

- RoamingDevices

  Intune y otras configuraciones del dispositivo especifican el uso de la red de Microsoft 365 para las instalaciones y actualizaciones.

## <a name="new-onboarding-process"></a>Nuevo proceso de incorporación

Para un nuevo dispositivo local dedicado emitido a un nuevo trabajo o para un nuevo servidor en un centro de datos, cuando el trabajo inicia sesión, el cliente Configuration Manager en función de la pertenencia del dispositivo al grupo OnPremDevices descarga e instala las actualizaciones más recientes para Windows 10, Aplicaciones Microsoft 365 para empresas y Edge desde puntos de distribución locales Configuration Manager. Una vez completado, el dispositivo local dedicado está listo para su uso y usa estos puntos de distribución para las actualizaciones en curso.

Para un nuevo dispositivo remoto emitido a un nuevo trabajo, cuando el trabajador inicia sesión, el dispositivo, en función de su pertenencia al grupo RoamingDevices, se pone en contacto con el servicio en la nube Intune y otros servicios y descarga e instala las actualizaciones más recientes para Windows 10, Aplicaciones Microsoft 365 para empresas y Edge. Una vez completado, el dispositivo remoto está listo para su uso y usa el cliente VPN instalado para acceder a los recursos locales y a la red de Microsoft 365 para las actualizaciones en curso.

## <a name="next-step"></a>Paso siguiente

[Configure la infraestructura para el trabajo híbrido](empower-people-to-work-remotely.md) en su organización.
