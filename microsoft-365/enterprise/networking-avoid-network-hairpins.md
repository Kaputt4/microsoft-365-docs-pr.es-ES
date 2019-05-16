---
title: 'Paso 3: Evitar las redirecciones de red'
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
description: Obtenga información y elimine las redirecciones de red para mejorar el rendimiento.
ms.openlocfilehash: eb233c02d1d4c0198c11d520acca1d680df78a82
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073290"
---
# <a name="step-3-avoid-network-hairpins"></a>Paso 3: Evitar las redirecciones de red

*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Una [redirección de red](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) se produce cuando el tráfico enlazado a un destino se dirige primero a otra ubicación intermedia, como por ejemplo a una pila de seguridad local, a un agente de acceso en la nube o a una puerta de enlace basada en la nube. Una redirección de red también se podría deber a un enrutamiento incorrecto en Internet debido a los proveedores de servicios de red. Una redirección de red agrega latencia y puede redirigir potencialmente el tráfico a una ubicación lejana geográficamente.

Para optimizar el rendimiento del tráfico a los servicios basados en la nube de Microsoft 365, compruebe si el ISP que proporciona la conexión local a Internet tiene una relación de emparejamiento directa con la Red global de Microsoft cerca de esa ubicación. Estas conexiones no tienen redirecciones de red.

Si usa servicios de red o seguridad basados en la nube para el tráfico de Microsoft 365, asegúrese de que se evalúa el efecto de la redirección de red y que se entiende su impacto en el rendimiento. Examine lo siguiente:

- El número y las ubicaciones de los proveedores de servicios a través de los que se reenvía el tráfico en relación con las sucursales y los puntos de emparejamiento de la red global de Microsoft 
- La calidad de la relación de emparejamiento de red del proveedor de servicios con el ISP y Microsoft 
- Impacto en el rendimiento del redireccionamiento en la infraestructura del proveedor de servicios

Siempre que sea posible, configure los enrutadores perimetrales para enviar directamente el tráfico de Microsoft 365 de confianza, en lugar de a través de un proxy o túnel mediante un proveedor de seguridad de red de terceros en la nube o basado en la nube que procesa el tráfico de Internet. 

Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step3) de este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Configurar la omisión de tráfico](networking-configure-proxies-firewalls.md)|
