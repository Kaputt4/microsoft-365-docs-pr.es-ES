---
title: 'Paso 4: Planear los cambios de direcciones IP y URL'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 44990dcfd09e5cc2a44666da43fdeeaffd59da7d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871149"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>Paso 4: Planear los cambios de direcciones IP y URL

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>Antes de este paso, es necesario completar el [Paso 3](networking-configure-proxies-firewalls.md). Si no completó el paso 3, puede ir directamente al [Paso 5](networking-optimize-tcp-performance.md).
>

Las direcciones IP y URL usadas por la red global de Microsoft 365 cambian con el tiempo, por lo que es importante planear las actualizaciones de estos puntos de conexión. Por ejemplo, puede que necesite volver a configurar los dispositivos del perímetro de seguridad con:

- Nuevas URL para nuevos servicios que necesiten un procesamiento sin restricciones.
- URL eliminadas de los servicios descontinuados.
- Nuevos intervalos de direcciones IP para las nuevas ubicaciones de red y servidores de Microsoft en Internet. 
- Cambios en los intervalos de direcciones IP para los distintos servicios.

Para obtener más información sobre cómo establecer un plan de implementación para los cambios en los puntos de conexión, incluidas las notificaciones de cambios, vea [Administrar los puntos de conexión de Office 365: Integración](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) y [Administrar los puntos de conexión de Office 365: Servidores proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).

Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step4) de este paso.

## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Optimizar el rendimiento del servicio de Office 365 y el cliente](networking-optimize-tcp-performance.md)|
