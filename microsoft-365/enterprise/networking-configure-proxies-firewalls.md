---
title: 'Paso 4: Configurar la omisión de tráfico'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información y configure los exploradores web y los dispositivos perimetrales para la omisión de tráfico a ubicaciones de confianza de Office 365.
ms.openlocfilehash: fbc4956525e2661ce791c6ec81b449dba685d0f0
ms.sourcegitcommit: 1ca1062ccddd7a46fa0bb4af6ee5f0eb141e7280
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2019
ms.locfileid: "36999044"
---
# <a name="step-4-configure-traffic-bypass"></a>Paso 4: Configurar la omisión de tráfico

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Como el tráfico de Internet general puede ser peligroso, en las redes de organización típicas se aplica la seguridad con dispositivos perimetrales como servidores proxy, inspección e interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos. En Uso de dispositivos de red o soluciones de terceros para el tráfico de Office 365 encontrará información sobre algunos de los problemas con los dispositivos de interceptación de red.

Pero los nombres de dominio DNS y las direcciones IP que se usan en los servicios basados en la nube de Microsoft 365 son conocidos. Además, el tráfico y los propios servicios están protegidos con muchas características de seguridad. Como esta protección y seguridad ya está aplicada, no es necesario que los dispositivos perimetrales la dupliquen. Los destinos intermedios y el procesamiento de seguridad duplicado para el tráfico de Microsoft 365 pueden reducir considerablemente el rendimiento.

El primer paso para eliminar los destinos intermedios y el procesamiento duplicado de la seguridad consiste en identificar el tráfico de Microsoft 365. Microsoft ha definido los siguientes tipos de nombres de dominio DNS e intervalos de direcciones IP, conocidos como puntos de conexión:

- **Optimizar**: obligatorios para la conectividad a todos los servicios de Office 365 y representan más del 75 % del ancho de banda, las conexiones y el volumen de datos de Microsoft 365. Estos puntos de conexión representan escenarios de Microsoft 365 que son más sensibles al rendimiento, la latencia y la disponibilidad de la red.
- **Permitir**: obligatorios para la conectividad a características y servicios específicos de Microsoft 365, pero no son tan sensibles al rendimiento y la latencia de la red como los de la categoría Optimizar.
 - **Predeterminados**: representan servicios y dependencias de Microsoft 365 que no requieren ninguna optimización. Puede tratar los puntos de conexión de la categoría Predeterminados como tráfico de Internet normal.

Puede encontrar los nombres de dominio DNS y los intervalos de direcciones IP en [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).

Microsoft le recomienda:

- Usar scripts de Configuración automática de proxy (PAC) en los exploradores de Internet de los equipos locales para omitir los servidores proxy de los nombres de dominio DNS de los servicios basados en la nube de Microsoft 365. Para obtener el script PAC de Microsoft 365 más reciente, vea el [script Get-Pacfile de PowerShell](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).
- 
- Analizar los dispositivos perimetrales para determinar el procesamiento duplicado y configurarlos para reenviar el tráfico a puntos de conexión de la categoría Optimizar y Permitir sin procesamiento. Esto se conoce como omisión de tráfico. 

Los dispositivos perimetrales incluyen firewalls, inspección e interrupción SSL, dispositivos de inspección de paquetes y sistemas de prevención de pérdida de datos. Para configurar y actualizar las configuraciones de los dispositivos perimetrales, puede usar un script o una llamada REST para consumir una lista estructurada de puntos de conexión del servicio web Puntos de conexión de Office 365. Para obtener más información, vea [Dirección IP de Office 365 y servicio web de URL](https://docs.microsoft.com/es-ES/office365/enterprise/office-365-ip-web-service#exporting-a-proxy-pac-file).

Tenga en cuenta que solo se omite el procesamiento de seguridad de red y proxy normal para el tráfico a los puntos de conexión de las categorías Optimizar y Permitir de Microsoft 365. El resto del tráfico general de Internet se dirige a través de un proxy y se somete al procesamiento de seguridad de red existente.


Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step4) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Optimizar el rendimiento del servicio de Office 365 y el cliente](networking-optimize-tcp-performance.md) |



