---
title: Guía de redes para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
description: La guía básica para implementar redes de Microsoft 365.
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693918"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Guía de redes para Microsoft 365

Microsoft 365 para empresas incluye servicios en la nube de colaboración y productividad, Microsoft Intune y muchos servicios de identidad y seguridad de Microsoft Azure. Todos estos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados. Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración. 

Una parte fundamental de la incorporación de Microsoft 365 es asegurarse de que la red y las conexiones de Internet están configuradas para un acceso optimizado. La configuración de la red local para tener acceso a una nube de software como servicio (SaaS) distribuida globalmente es diferente de una red tradicional optimizada para el tráfico a los centros de recursos locales y una conexión a Internet central. 

Use estos artículos para comprender las principales diferencias, así como para modificar los dispositivos perimetrales, los equipos cliente y la red local a fin de obtener el mejor rendimiento para sus usuarios locales.

## <a name="plan"></a>Plan

En la fase de planeación de la implementación de red:

- [Comprender cómo funciona la red de Microsoft 365](microsoft-365-networking-overview.md)
- [Evaluar la conectividad de red actual](assessing-network-connectivity.md)
- [Determinar si ExpressRoute es el adecuado para su organización](network-planning-with-expressroute.md)
- [Planeación de los dispositivos de red](plan-for-network-devices.md)
- [Preparar la red para la migración](network-and-migration-planning.md)

## <a name="deploy"></a>Implementar

En la fase de implementación de la implementación de la red:

- [Asegurarse de que la red empresarial está optimizada para la conectividad de Microsoft 365](set-up-network-for-microsoft-365.md)
- [Adición de los dominios DNS para la organización](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Optimizar la conectividad con los puntos de conexión de 365 de Microsoft](microsoft-365-ip-web-service.md)
- [Optimizar la conectividad para los trabajadores remotos](microsoft-365-vpn-split-tunnel.md)
- Si es necesario, [Configure ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Manage

En la fase de administración de la implementación de la red:

- [Asegurarse de que los dispositivos de red usan los puntos de conexión de Office 365 más recientes](microsoft-365-endpoints.md)
- [Supervisar y ajustar el rendimiento de la red](network-planning-and-performance.md)
- [Supervisar las conexiones de ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Proveedores de equipos de red

Si es un proveedor de equipos de red, únase al [programa de asociados de red de Microsoft 365](microsoft-365-networking-partner-program.md). Inscríbase en el programa para crear principios de conectividad de red de Microsoft 365 en sus productos y soluciones. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Cómo contoso realizó redes para Microsoft 365

Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó sus dispositivos de red y conexión a Internet](contoso-networking.md) para los servicios en la nube de Microsoft 365.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Paso siguiente

Inicie la planeación de red con la [Introducción a la conectividad de red de Microsoft 365](microsoft-365-networking-overview.md).
