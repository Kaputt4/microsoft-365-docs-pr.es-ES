---
title: 'Paso 3: Evitar las redirecciones de red'
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
description: Obtenga información y elimine las redirecciones de red para mejorar el rendimiento.
ms.openlocfilehash: 8d3c971c1295f8f1112c594635bfd791b251bd68
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370337"
---
# <a name="step-3-avoid-network-hairpins"></a>Paso 3: Evitar las redirecciones de red

*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![Fase 1-Red](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Una [redirección de red](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) ocurre cuando el tráfico vinculado a un destino se dirige por primera vez a otra ubicación intermedia, como una pila de seguridad local, un agente de acceso a la nube o una puerta de enlace web basada en la nube. Aquí le mostramos un ejemplo.

![Ejemplo de una redirección de red](./media/networking-avoid-network-hairpins/network-hairpin-example.png)

Una redirección de red también puede deberse a un bajo enrutamiento en Internet debido a los proveedores de servicios de red. 

Una redirección de red agrega latencia y puede redirigir potencialmente el tráfico a una localización geográficamente lejana.

Para optimizar el rendimiento del tráfico a los servicios basados en la nube de Microsoft 365, compruebe si el ISP que proporciona la conexión local a Internet tiene una relación de emparejamiento directa con la Red global de Microsoft cerca de esa ubicación. Estas conexiones no tienen redirecciones de red.

Si usa servicios de red o seguridad basados en la nube para el tráfico de Microsoft 365, asegúrese de que se evalúa el efecto de la redirección de red y que se entiende su impacto en el rendimiento. Examine lo siguiente:

- El número y las ubicaciones de los proveedores de servicios a través de los que se reenvía el tráfico en relación con las sucursales y los puntos de emparejamiento de la red global de Microsoft 
- La calidad de la relación de emparejamiento de red del proveedor de servicios con el ISP y Microsoft 
- Impacto en el rendimiento del redireccionamiento en la infraestructura del proveedor de servicios

Siempre que sea posible, configure los enrutadores perimetrales para enviar directamente el tráfico de Microsoft 365 de confianza, en lugar de a través de un proxy o túnel mediante un proveedor de seguridad de red de terceros en la nube o basado en la nube que procesa el tráfico de Internet. 

![Ejemplo de cómo evitar una redirección de red](./media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step3) de este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 4](./media/stepnumbers/Step4.png)|[Configurar la omisión de tráfico](networking-configure-proxies-firewalls.md)|
