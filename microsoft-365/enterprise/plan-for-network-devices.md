---
title: Planificación de dispositivos de red que se conecten a servicios de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Resumen: describe las consideraciones sobre la capacidad de red, los aceleradores WAN y los dispositivos de equilibrio de carga que se usan para conectarse a Office 365.'
ms.openlocfilehash: 385b4ccf862e47581b42e07c72ae6cc14ecb0975
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195641"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Planificación de dispositivos de red que se conecten a servicios de Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*
  
Algunos hardware de red pueden tener limitaciones en el número de sesiones simultáneas que se admiten. Para las organizaciones que tienen más de 2000 usuarios, se recomienda supervisar sus dispositivos de red para asegurarse de que son capaces de controlar el tráfico adicional Office 365 servicio. El software de supervisión simple del Protocolo de administración de redes (SNMP) puede ayudarle a hacerlo.

Este artículo forma parte del [planeamiento de la red y la optimización del rendimiento para Office 365](./network-planning-and-performance.md).

La configuración del proxy de Internet saliente local también afecta a la conectividad a los servicios de Office 365 para las aplicaciones cliente. También debe configurar los dispositivos proxy de red para permitir conexiones para las direcciones URL y las aplicaciones de los servicios en la nube de Microsoft. Cada organización es diferente. Para hacerse una idea de cómo Microsoft administra este proceso y la cantidad de ancho de banda que aprovisionamos, [lea el caso práctico](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
Los siguientes artículos de la Ayuda Skype Empresarial tienen más información sobre la configuración de Skype Empresarial:
  
- [Solución de problemas Skype Empresarial errores de inicio de sesión en línea para administradores](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [No se puede conectar a Skype Empresarial, o algunas características no funcionan, porque un firewall local bloquea la conexión.](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Aunque muchas de estas opciones de configuración son específicas de Skype Empresarial, las instrucciones generales sobre la configuración de red son útiles para todos los servicios de Office 365.
  
## <a name="determining-network-capacity"></a>Determinación de la capacidad de red

Cada dispositivo de red que existe en una conexión tiene su límite de capacidad. Estos dispositivos incluyen los adaptadores de red de cliente y servidor, enrutadores, conmutadores y concentradores que los interconectan. Una capacidad de red adecuada significa que ninguna de ellas está saturada. La supervisión de la actividad de red es esencial para garantizar que las cargas reales en todos los dispositivos de red sean inferiores a su capacidad máxima. La capacidad de red afecta al rendimiento del dispositivo proxy.
  
En la mayoría de las situaciones, el ancho de banda de conexión a Internet establece el límite para la cantidad de tráfico. El rendimiento débil durante las horas punta del tráfico probablemente se debe al uso excesivo del vínculo a Internet. Esta situación también se aplica a un escenario de sucursal, donde los equipos de servidor proxy de sucursal están conectados al dispositivo proxy en la sede central de la rama a través de un vínculo de red de área extensa (WAN) lento.
  
Para probar la capacidad de red, supervise la actividad de red en la interfaz de red proxy. Si es más del 75 % del ancho de banda máximo de cualquier interfaz de red, considere la posibilidad de aumentar el ancho de banda de la infraestructura de red que sea inadecuado. O bien, considere la posibilidad de usar características avanzadas, como la compresión HTTP.
  
## <a name="wan-accelerators"></a>Aceleradores WAN

Si su organización usa aplicaciones de proxy de aceleración de red de área extensa (WAN), es posible que se produzcan problemas al acceder a los servicios de Office 365. Es posible que tenga que optimizar el dispositivo o los dispositivos de red para asegurarse de que los usuarios tengan una experiencia coherente al acceder a Office 365. Por ejemplo, Office 365 servicios cifran algunos Office 365 contenido y el encabezado TCP. Es posible que el dispositivo no pueda controlar este tipo de tráfico.
  
Lea nuestra declaración de soporte técnico sobre [el uso del controlador de optimización WAN o los dispositivos de tráfico/inspección con Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivos de equilibrio de carga de hardware y software

La organización debe usar un equilibrador de carga de hardware (HLB) o una solución de equilibrio de carga de red (NLB) para distribuir las solicitudes a los servidores de Servicios de federación de Active Directory (AD FS) (AD FS) o a los servidores híbridos de Exchange. Los dispositivos de equilibrio de carga controlan el tráfico de red a los servidores locales. Estos servidores son fundamentales para ayudar a garantizar la disponibilidad del inicio de sesión único y la implementación híbrida de Exchange.
  
Proporcionamos una solución NLB basada en software integrada en Windows Server. Office 365 admite esta solución para lograr el equilibrio de carga.
  
## <a name="firewalls-and-proxies"></a>Firewalls y servidores proxy

Para obtener más información sobre cómo configurar firewalls y servidores proxy para conectarse a Office 365, consulte [Administración de puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Evaluación de Office 365 conectividad de red](assessing-network-connectivity.md) y [preguntas más frecuentes sobre puntos de conexión de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) para obtener más información sobre los dispositivos y la selección de circuitos.
  
## <a name="see-also"></a>Vea también

[Guías de configuración para servicios de Office 365](setup-guides-for-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)