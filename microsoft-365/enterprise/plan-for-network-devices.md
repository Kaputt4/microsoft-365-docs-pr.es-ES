---
title: Planificación de dispositivos de red que se conecten a servicios de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Resumen: describe consideraciones sobre la capacidad de red, los aceleradores WAN y los dispositivos de equilibrio de carga que se usan para conectarse a Office 365.'
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927505"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Planificación de dispositivos de red que se conecten a servicios de Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*
  
Algunos hardware de red pueden tener limitaciones en el número de sesiones simultáneas admitidas. Para las organizaciones que tienen más de 2.000 usuarios, se recomienda supervisar sus dispositivos de red para asegurarse de que son capaces de controlar el tráfico de Office 365 servicio adicional. El software de supervisión simple del Protocolo de administración de red (SNMP) puede ayudarle a hacerlo.

Este artículo forma parte de [la planeación de red y el](./network-planning-and-performance.md)ajuste del rendimiento para Office 365 .

La configuración de proxy de Internet saliente local también afecta a la conectividad a Office 365 servicios de las aplicaciones cliente. También debe configurar los dispositivos proxy de red para permitir conexiones para aplicaciones y direcciones URL de servicios en la nube de Microsoft. Cada organización es diferente. Para obtener una idea de cómo Microsoft administra este proceso y la cantidad de ancho de banda que aprovisionamos, [lea el caso práctico](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
Los siguientes Skype Empresarial artículos de ayuda tienen más información sobre Skype Empresarial configuración:
  
- [Solución de Skype Empresarial errores de inicio de sesión en línea para administradores](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [No puede conectarse a Skype Empresarial, o determinadas características no funcionan, porque un firewall local bloquea la conexión](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Aunque muchas de estas opciones de configuración Skype Empresarial específicos, las instrucciones generales sobre la configuración de red son útiles para todos los Office 365 configuración.
  
## <a name="determining-network-capacity"></a>Determinación de la capacidad de red

Cada dispositivo de red que existe en una conexión tiene su límite de capacidad. Estos dispositivos incluyen adaptadores de red de cliente y servidor, enrutadores, conmutadores y concentradores que los interconectan. La capacidad de red adecuada significa que ninguno de ellos está saturado. La supervisión de la actividad de red es esencial para garantizar que las cargas reales en todos los dispositivos de red sean inferiores a su capacidad máxima. La capacidad de red afecta al rendimiento del dispositivo proxy.
  
En la mayoría de las situaciones, el ancho de banda de conexión a Internet establece el límite para la cantidad de tráfico. El rendimiento débil durante las horas pico de tráfico probablemente se debe al uso excesivo del vínculo a Internet. Esta situación también se aplica a un escenario de sucursal, donde los equipos de servidor proxy de sucursal están conectados al dispositivo proxy en la sede de la sucursal a través de un vínculo de red de área extensa (WAN) lento.
  
Para probar la capacidad de red, supervise la actividad de red en la interfaz de red proxy. Si es más del 75 por ciento del ancho de banda máximo de cualquier interfaz de red, considere la posibilidad de aumentar el ancho de banda de la infraestructura de red que no es adecuado. O bien, considere el uso de características avanzadas, como la compresión HTTP.
  
## <a name="wan-accelerators"></a>Aceleradores WAN

Si su organización usa dispositivos proxy de aceleración de red de área extensa (WAN), es posible que tenga problemas al acceder a los servicios Office 365 área extensa. Es posible que deba optimizar su dispositivo o dispositivos de red para garantizar que los usuarios tengan una experiencia coherente al acceder a Office 365. Por ejemplo, Office 365 cifrado de algunos Office 365 contenido y el encabezado TCP. Es posible que el dispositivo no pueda controlar este tipo de tráfico.
  
Lea nuestra declaración de soporte técnico sobre el uso del controlador [de optimización WAN o los dispositivos de tráfico/inspección con Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivos de equilibrio de carga de hardware y software

Su organización debe usar un equilibrador de carga de hardware (HLB) o una solución de equilibrio de carga de red (NLB) para distribuir las solicitudes a los servidores de servicios de federación de Active Directory (AD FS) o a los servidores híbridos de Exchange. Los dispositivos de equilibrio de carga controlan el tráfico de red a los servidores locales. Estos servidores son fundamentales para ayudar a garantizar la disponibilidad del inicio de sesión único y la Exchange implementación híbrida.
  
Proporcionamos una solución NLB basada en software integrada en Windows Server. Office 365 esta solución para lograr el equilibrio de carga.
  
## <a name="firewalls-and-proxies"></a>Firewalls y servidores proxy

Para obtener más información sobre cómo configurar firewalls y servidores proxy para conectarse a Office 365, consulte Managing [Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Assessing Office 365 network connectivity](assessing-network-connectivity.md)y Office 365 [endpoints FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) to learn more about devices and circuit selection.
  
## <a name="see-also"></a>Consulte también

[Guías de instalación para Office 365 servicios](setup-guides-for-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)