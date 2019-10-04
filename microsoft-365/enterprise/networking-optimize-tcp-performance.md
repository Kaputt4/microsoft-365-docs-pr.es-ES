---
title: 'Paso 5: Optimizar el rendimiento del servicio de Office 365 y el cliente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Configure las opciones de TCP y los servicios de Office 365 para obtener un mejor rendimiento.
ms.openlocfilehash: f89ae816780101c31971c8e3e60df803f82f1e55
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370077"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Paso 5: Optimizar el rendimiento del servicio de Office 365 y el cliente

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![Fase 1-Red](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Puede aumentar el rendimiento si ajusta la forma en que el Protocolo de control de transmisión (TCP) funciona entre los dispositivos cliente y los servicios de Office 365.

Puede cambiar las siguientes opciones de configuración de TCP en los dispositivos cliente para optimizar el rendimiento de TCP:

- [Escalado de ventana de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que el dispositivo cliente pueda enviar más datos antes de exigir una confirmación.
- [Tiempo de inactividad de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que el dispositivo cliente pueda administrar las conexiones abiertas de forma más eficiente.
- [Tamaño máximo del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que el dispositivo cliente pueda enviar los bloques de datos de mayor tamaño en un paquete.
- [Confirmaciones selectivas de TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que el dispositivo cliente pueda confirmar los datos recibidos de forma más eficiente.

Para los servicios de Office 365, vea estos recursos adicionales para optimizar el rendimiento:

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype Empresarial Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App en Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step5) de este paso.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de red](networking-exit-criteria.md)
