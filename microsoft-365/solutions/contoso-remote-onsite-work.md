---
title: Respuesta y soporte de COVID-19 de Contoso para el trabajo remoto e in situ
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo Contoso Corporation ha respondido a la pandemia de COVID-19 y ha diseñado su infraestructura de instalación y actualización de software para el trabajo remoto e in situ.
ms.openlocfilehash: d04b4efcdd4dd04315ad37311cdd2cfbc2e64e88
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580678"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Respuesta y soporte de COVID-19 de Contoso para el trabajo remoto e in situ

Contoso siempre había admitido a sus trabajadores remotos, que accedieron a los recursos locales a través de un servidor VPN central en la sede de París. Contoso había emitido a todos los trabajadores remotos un portátil administrado. Los trabajadores locales tenían una combinación de equipos de escritorio y portátiles.

## <a name="contosos-response-to-covid-19"></a>Respuesta de Contoso a COVID-19

Con el inicio de la pandemia COVID-19, de pronto todos los trabajadores, menos los esenciales, eran trabajadores remotos. Contoso respondió cambiando su personal para trabajar desde casa y llevar a cabo sus actividades principales a través del acceso remoto a los recursos locales y en línea mediante los servicios en la nube de Microsoft 365.

Contoso tenía servidores VPN de acceso remoto en la oficina central de París para dar soporte al 25 % de su personal ya remoto, pero rápidamente se movió para ampliar su capacidad de acceso remoto para admitir el 90 % de su personal. Contoso implementó servidores VPN de acceso remoto en cada oficina satélite para que los trabajadores remotos usarían un punto de entrada de cierre regional para obtener acceso a la intranet de Contoso.

Contoso también actualizó la configuración de los clientes VPN instalados en portátiles, tabletas y teléfonos inteligentes para el túnel dividido, de modo que el tráfico del conjunto Optimizar de puntos de conexión de Office 365 omitió la conexión VPN y se envió directamente a través de Internet. Para obtener más información, vea Optimizar la [conectividad de Office 365](../enterprise/microsoft-365-vpn-split-tunnel.md)para usuarios remotos que usan túnel dividido de VPN.

Esta es la configuración resultante con dispositivos VPN instalados en la sede de París y en cada una de las oficinas satélite. 

![Infraestructura vpn de Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Un trabajador remoto con el cliente VPN instalado usa DNS para encontrar la oficina más cercana regionalmente y se conecta al dispositivo VPN instalado allí. Con el túnel dividido, el tráfico a los puntos de conexión de Optimización de Microsoft 365 se envía directamente a la ubicación de red de Microsoft 365 más cercana regionalmente. El resto del tráfico se envía a través de la conexión VPN al dispositivo VPN.

## <a name="contosos-support-for-remote-and-onsite-work"></a>Compatibilidad de Contoso con el trabajo remoto e in situ

Después de realizar los cambios iniciales para dar soporte principalmente a los trabajadores remotos durante los bloqueos regionales, Contoso realizó cambios en la infraestructura para admitir el trabajo remoto e in situ en el que un trabajador podría ser:

- Siempre remoto.
- Siempre in situ.
- Una combinación de instalación in situ y remota.

Las características de identidad, seguridad y cumplimiento de Microsoft 365 están diseñadas para la confianza cero y para funcionar independientemente de la ubicación del usuario y su dispositivo. Para obtener más información, vea [Confianza cero.](https://www.microsoft.com/security/business/zero-trust)

Sin embargo, la administración de nuevas instalaciones y actualizaciones de software depende de la ubicación del dispositivo, ya que el software que se va a instalar puede provienen de un origen de Internet o local. Los arquitectos de TI de Contoso diseñaron sus nuevas instalaciones y actualiza la infraestructura en función de la ubicación del dispositivo, en lugar del trabajador.

Designaron dos tipos de dispositivos: local dedicado y móvil.

### <a name="dedicated-on-premises"></a>Dedicado local

Un dispositivo local dedicado es un equipo de escritorio o servidor que nunca sale de la intranet de Contoso y no tiene instalado un cliente VPN. Estos dispositivos locales siguen usando Microsoft Endpoint Configuration Manager y sus puntos de distribución para las instalaciones y actualizaciones de Windows 10, Aplicaciones de Microsoft 365 para empresas y el explorador Edge.

### <a name="roaming"></a>Itinerancia

Un dispositivo móvil puede salir de la intranet de Contoso e incluye portátiles emitidos para muchos trabajadores de oficina y todos los trabajadores remotos y otros dispositivos propiedad de la organización, como teléfonos inteligentes y tabletas con el cliente VPN de Contoso instalado. 

Dado que estos dispositivos pueden conectarse a Internet en cualquier momento, usan Intune u otros servicios basados en la nube para instalar y actualizar Windows 10, Aplicaciones de Microsoft 365 para empresas y Edge. No usan los puntos de distribución locales existentes de Configuration Manager.

Esto significa que algunas de las instalaciones y actualizaciones del dispositivo móvil se realizarán a través de Internet mientras están locales y conectadas a la intranet. Pero los arquitectos de IT de Contoso han decidido que la simplicidad de configuración es más importante que la optimización del ancho de banda de intranet a Internet, especialmente cuando la mayoría de los trabajadores remotos rara vez están conectados a la intranet.

Esta es la infraestructura resultante.

![Infraestructura de instalación y actualización de Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

El comportamiento de instalación y actualización se determina haciendo que las cuentas de equipo de los dispositivos sea miembro de uno de estos grupos:

- OnPremDevices

  El cliente de Configuration Manager del dispositivo usa puntos de distribución para instalar y actualizar.

- RoamingDevices

  Intune y otras opciones de configuración del dispositivo especifican el uso de la red de Microsoft 365 para las instalación y las actualizaciones.

## <a name="new-onboarding-process"></a>Nuevo proceso de incorporación

Para un nuevo dispositivo local dedicado emitido para un nuevo trabajador o para un nuevo servidor en un centro de datos, cuando el trabajador inicia sesión, el cliente de Configuration Manager en función de la pertenencia del dispositivo en el grupo OnPremDevices descarga e instala las actualizaciones más recientes para Windows 10, Aplicaciones de Microsoft 365 para empresas y Edge desde puntos de distribución locales de Configuration Manager. Una vez completado, el dispositivo local dedicado está listo para su uso y usa estos puntos de distribución para actualizaciones continuas.

Para un nuevo dispositivo remoto emitido a un nuevo trabajador, cuando el trabajador inicia sesión, el dispositivo, en función de su pertenencia al grupo RoamingDevices, se pone en contacto con el servicio en la nube de Intune y otros servicios y descarga e instala las actualizaciones más recientes para Windows 10, Aplicaciones de Microsoft 365 para empresas y Edge. Una vez completado, el dispositivo remoto está listo para usarse y usa el cliente VPN instalado para obtener acceso a recursos locales y a la red de Microsoft 365 para actualizaciones continuas.

## <a name="next-step"></a>Paso siguiente

[Dar poder a los trabajadores remotos](empower-people-to-work-remotely.md) de su organización.
