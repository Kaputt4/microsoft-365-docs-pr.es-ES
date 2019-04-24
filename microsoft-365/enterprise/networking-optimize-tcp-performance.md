---
title: 'Paso 5: Optimizar el rendimiento del servicio de Office 365 y el cliente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Configure las opciones de TCP y los servicios de Office 365 para obtener un mejor rendimiento.
ms.openlocfilehash: cf172bcaa87b7c69d33d349d18c449efff30a1d9
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290887"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Paso 5: Optimizar el rendimiento del servicio de Office 365 y el cliente

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Puede aumentar el rendimiento si ajusta la forma en que el Protocolo de control de transmisión (TCP) funciona entre los dispositivos cliente y los servicios de Office 365.

Puede cambiar las siguientes opciones de configuración de TCP en los dispositivos cliente para optimizar el rendimiento de TCP:

- [Escalado de ventana de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que el dispositivo cliente pueda enviar más datos antes de exigir una confirmación.
- [Tiempo de inactividad de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que el dispositivo cliente pueda administrar las conexiones abiertas de forma más eficiente.
- [Tamaño máximo del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que el dispositivo cliente pueda enviar los bloques de datos de mayor tamaño en un paquete.
- [Confirmaciones selectivas de TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que el dispositivo cliente pueda confirmar los datos recibidos de forma más eficiente.

Para los servicios de Office 365, vea estos recursos adicionales para optimizar el rendimiento:

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype Empresarial Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step5) de este paso.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de red](networking-exit-criteria.md)
