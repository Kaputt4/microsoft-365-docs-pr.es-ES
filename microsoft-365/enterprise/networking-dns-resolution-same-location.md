---
title: 'Paso 2: Configurar conexiones a Internet locales para cada oficina'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure su resolución DNS para mejorar el rendimiento.
ms.openlocfilehash: 6f276bd1fd90b8dee76a0b0d350f256956ded412
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291135"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Paso 2: Configurar conexiones a Internet locales para cada oficina

*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

En el paso 2, se asegura de que todas las oficinas tienen conexión local a Internet y usan servidores DNS locales. Estos dos elementos son necesarios para reducir la latencia de la conexión y asegurarse de que los equipos cliente locales establecen conexiones con el punto de entrada más próximo a los servicios basados en la nube de Microsoft 365.

En las redes tradicionales para grandes organizaciones, el tráfico de Internet viaja a través de la red troncal a una conexión a Internet central. Esto no funciona bien para optimizar el rendimiento de una infraestructura de Software como-servicio (SaaS) distribuida de forma global, que incluye los productos Office 365 y Enterprise Mobility + productos Security (EMS) de Microsoft 365.

La red global de Microsoft incluye servidores front-end para el conjunto de servicios de nube de Microsoft 365 en todo el mundo. Para obtener el mejor rendimiento, los clientes locales deben acceder a un servidor front-end geográficamente más próximo a ellos, en lugar de enviar el tráfico a través de una red troncal al servidor front-end más próximo a la conexión de Internet central de la organización.

Para dirigir una solicitud cliente al servidor front-end más cercano geográficamente, los servidores DNS de Microsoft usan las consultas DNS correspondientes a la solicitud de conexión inicial del cliente. Por tanto, para obtener la latencia de red más baja:

- Todas las oficinas de la organización deben tener conexiones locales a Internet para el tráfico de red de la categoría [Optimizar](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).
- Todas las conexiones locales a Internet deben usar un servidor DNS local de la región para el tráfico de Internet saliente desde esa ubicación.

Para obtener más información, vea [Conexiones de red de salida de forma local](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally). 

Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step2) de este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Evitar las redirecciones de red](networking-avoid-network-hairpins.md)|
