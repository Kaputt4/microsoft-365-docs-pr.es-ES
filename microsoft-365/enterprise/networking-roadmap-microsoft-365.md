---
title: Plan de trabajo de redes para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/03/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: La hoja de ruta para planear, implementar y administrar redes de Microsoft 365.
ms.openlocfilehash: 868ec406522f9bd35e0087089d8fb8ce6b5c3e26
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185279"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Plan de trabajo de redes para Microsoft 365

Microsoft 365 para empresas incluye servicios en la nube de colaboración y productividad, Microsoft Intune y muchos servicios de identidad y seguridad de Microsoft Azure. Todos estos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados. Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración.

Una parte fundamental de la incorporación de Microsoft 365 es asegurarse de que la red y las conexiones a Internet están configuradas para un acceso optimizado. La configuración de la red local para acceder a una nube de software como servicio (SaaS) distribuida globalmente es diferente de una red tradicional optimizada para el tráfico a centros de datos locales y una conexión central a Internet.

Use estos artículos para comprender las principales diferencias, así como para modificar los dispositivos perimetrales, los equipos cliente y la red local a fin de obtener el mejor rendimiento para sus usuarios locales.

## <a name="plan"></a>Plan

En la fase de planeación de la implementación de redes:

- [Descripción del funcionamiento de las redes de Microsoft 365](microsoft-365-networking-overview.md)
- [Más información sobre los principios de conectividad de red](microsoft-365-network-connectivity-principles.md)
- [Evaluación de la conectividad de red actual](assessing-network-connectivity.md)
- [Determinar si ExpressRoute es adecuado para su organización](network-planning-with-expressroute.md)
- [Planeamiento de los dispositivos de red](plan-for-network-devices.md)
- [Configuración de la red para la migración](network-and-migration-planning.md)

## <a name="deploy"></a>Implementar

En la fase de implementación de la implementación de redes:

- [Asegúrese de que la red empresarial está optimizada para la conectividad de Microsoft 365](set-up-network-for-microsoft-365.md)
- [Agregar los dominios DNS para su organización](../admin/setup/add-domain.md)
- [Optimización de la conectividad para los trabajadores remotos mediante la tunelización dividida de VPN](microsoft-365-vpn-split-tunnel.md)
- [Configuración de la red CDN para mejorar el rendimiento de la red](office-365-cdn-quickstart.md)
- [Optimización de la conectividad con puntos de conexión de Microsoft 365](microsoft-365-ip-web-service.md)
- Si es necesario, [configure ExpressRoute](azure-expressroute.md).

## <a name="manage"></a>Administrar

En la fase de administración de la implementación de redes:

- [Prueba y optimización mediante la herramienta de prueba de conectividad de red de Microsoft 365](office-365-network-mac-perf-onboarding-tool.md)
- [Asegúrese de que los dispositivos de red usan los puntos de conexión de Office 365 más recientes.](microsoft-365-endpoints.md)
- [Supervisión y optimización del rendimiento de las redes](network-planning-and-performance.md)
- [Supervisión de la conectividad de Microsoft 365](monitor-connectivity.md)

## <a name="network-equipment-vendors"></a>Proveedores de equipos de red

Si es un proveedor de equipos de red, únase al [Programa para partners de redes de Microsoft 365](microsoft-365-networking-partner-program.md). Inscríbase en el programa para crear principios de conectividad de red de Microsoft 365 en sus productos y soluciones.

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Cómo contoso hizo redes para Microsoft 365

Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó sus dispositivos de red y conexión a Internet](contoso-networking.md) para los servicios en la nube de Microsoft 365.

![The Contoso Corporation.](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Paso siguiente

Inicie el planeamiento de redes con la [introducción a la conectividad de red de Microsoft 365](microsoft-365-networking-overview.md).
