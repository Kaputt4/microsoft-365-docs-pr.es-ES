---
title: Guía básica de redes para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Guía básica para implementar Microsoft 365 red.
ms.openlocfilehash: 3fb9c99bd0381730a41bd65012efe5488b85509d
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58570058"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Guía básica de redes para Microsoft 365

Microsoft 365 para empresas incluye servicios en la nube de colaboración y productividad, Microsoft Intune y muchos servicios de identidad y seguridad de Microsoft Azure. Todos estos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados. Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración. 

Una parte fundamental de la incorporación Microsoft 365 es garantizar que las conexiones de red e Internet estén configuradas para un acceso optimizado. La configuración de la red local para tener acceso a una nube de Software como servicio (SaaS) distribuida globalmente es diferente de una red tradicional optimizada para el tráfico a centros de datos locales y una conexión central a Internet. 

Use estos artículos para comprender las principales diferencias, así como para modificar los dispositivos perimetrales, los equipos cliente y la red local a fin de obtener el mejor rendimiento para sus usuarios locales.

## <a name="plan"></a>Plan

En la fase de planeación de la implementación de redes:

- [Comprender cómo funciona Microsoft 365 de red](microsoft-365-networking-overview.md)
- [Evaluar la conectividad de red actual](assessing-network-connectivity.md)
- [Determinar si ExpressRoute es adecuado para su organización](network-planning-with-expressroute.md)
- [Planear los dispositivos de red](plan-for-network-devices.md)
- [Configurar la red para la migración](network-and-migration-planning.md)

## <a name="deploy"></a>Implementar

En la fase de implementación de la implementación de red:

- [Asegúrese de que la red empresarial está optimizada para Microsoft 365 conectividad](set-up-network-for-microsoft-365.md)
- [Agregar los dominios DNS de la organización](../admin/setup/add-domain.md)
- [Optimizar la conectividad a Microsoft 365 de conexión](microsoft-365-ip-web-service.md)
- [Optimizar la conectividad de los trabajadores remotos](microsoft-365-vpn-split-tunnel.md)
- Si es necesario, [configure ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Administrar

En la fase de administración de la implementación de redes:

- [Asegúrese de que los dispositivos de red usan los últimos Office 365 de conexión](microsoft-365-endpoints.md)
- [Supervisar y ajustar el rendimiento de las redes](network-planning-and-performance.md)
- [Supervisar las conexiones de ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Proveedores de equipamiento de red

Si es un proveedor de equipamiento de red, únase a [la Microsoft 365 Programa para partners de redes](microsoft-365-networking-partner-program.md). Inscríbase en el programa para crear Microsoft 365 principios de conectividad de red en sus productos y soluciones. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Cómo Contoso hizo las redes para Microsoft 365

Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó sus dispositivos de red y conexión a Internet](contoso-networking.md) para los servicios en la nube de Microsoft 365.

![The Contoso Corporation.](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Paso siguiente

Inicie la planeación de redes con [la Microsoft 365 de conectividad de red.](microsoft-365-networking-overview.md)