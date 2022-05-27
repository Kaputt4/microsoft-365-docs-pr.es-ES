---
title: Azure ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Obtenga información sobre cómo usar Azure ExpressRoute con Office 365 y planear el proyecto de implementación de red si va a realizar la implementación con él.
ms.openlocfilehash: 1350bf73fdddd2141a2df1cbcec5edebeacf7ad4
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65754298"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Obtenga información sobre cómo se usa Azure ExpressRoute con Office 365 y cómo planear el proyecto de implementación de red que será necesario si va a implementar Azure ExpressRoute para su uso con Office 365. Los servicios de infraestructura y plataforma que se ejecutan en Azure a menudo se beneficiarán de las consideraciones de rendimiento y arquitectura de red. En estos casos, se recomienda ExpressRoute para Azure. Las ofertas de software como servicio, como Office 365 y Dynamics 365, se han creado para acceder de forma segura y confiable a través de Internet. Puede leer sobre el rendimiento y la seguridad de Internet y cuándo podría considerar Azure ExpressRoute para Office 365 en el artículo [Evaluación de Office 365 conectividad de red](assessing-network-connectivity.md).

> [!NOTE]
> Microsoft Defender para punto de conexión no proporciona integración con Azure ExpressRoute. Aunque esto no impide que los clientes definan reglas de ExpressRoute que permitan la conectividad desde una red privada a Microsoft Defender para punto de conexión servicios en la nube, depende del cliente mantener las reglas a medida que evoluciona la infraestructura de servicio o nube.

> [!NOTE]
> No se recomienda ExpressRoute para Microsoft 365 porque no proporciona el mejor modelo de conectividad para el servicio en la mayoría de las circunstancias. Por lo tanto, se requiere autorización de Microsoft para usar este modelo de conectividad para Microsoft 365. Revisamos cada solicitud de cliente y autorizamos ExpressRoute para Microsoft 365 solo en los escenarios poco frecuentes en los que sea necesario. Lea la [guía expressroute para Microsoft 365](https://aka.ms/erguide) para obtener más información y, después de una revisión completa del documento con los equipos de productividad, red y seguridad, trabaje con el equipo de su cuenta Microsoft para enviar una excepción si es necesario. Las suscripciones no autorizadas que intentan crear filtros de ruta para Office 365 recibirán un [mensaje de error](https://support.microsoft.com/kb/3181709).

## <a name="planning-azure-expressroute-for-office-365"></a>Planeamiento de Azure ExpressRoute para Office 365

Además de la conectividad a Internet, puede optar por enrutar un subconjunto de su tráfico de red Office 365 a través de una conexión directa que ofrezca previsibilidad y un Acuerdo de Nivel de Servicio de tiempo de actividad del 99,95 % para los componentes de red de Microsoft. Azure ExpressRoute proporciona esta conexión de red dedicada a Office 365 y otros servicios en la nube de Microsoft.

Independientemente de si tiene una wan de MPLS existente, ExpressRoute se puede agregar a la arquitectura de red de una de tres maneras; a través de un proveedor de ubicación conjunta de intercambio en la nube compatible, un proveedor de conexiones de punto a punto Ethernet o a través de un proveedor de conexiones MPLS. Vea qué [proveedores están disponibles en su región](/azure/expressroute/expressroute-locations). La conexión directa de ExpressRoute habilitará la conectividad con las aplicaciones descritas en [¿Qué Office 365 servicios se incluyen](azure-expressroute.md#BKMK_WhatDoIGet) a continuación? El tráfico de red para todas las demás aplicaciones y servicios seguirá a través de Internet.

Tenga en cuenta el siguiente diagrama de red de alto nivel, que muestra un cliente Office 365 típico que se conecta a los centros de datos de Microsoft a través de Internet para acceder a todas las aplicaciones de Microsoft, como Office 365, Windows Update y TechNet. Los clientes usan una ruta de acceso de red similar independientemente de si se conectan desde una red local o desde una conexión a Internet independiente.

![Office 365 conectividad de red.](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Ahora examine el diagrama actualizado, que muestra un cliente Office 365 que usa Internet y ExpressRoute para conectarse a Office 365. Tenga en cuenta que algunas conexiones, como DNS público y nodos de Content Delivery Network, siguen necesitando la conexión pública a Internet. Observe también que los usuarios del cliente que no se encuentran en su edificio conectado a ExpressRoute se conectan a través de Internet.

![Office 365 conectividad con ExpressRoute.](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

¿Aún quieres más información? Aprenda a [administrar el tráfico de red con Azure ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) y a [configurar Azure ExpressRoute para Office 365](/azure/expressroute/expressroute-faqs). También hemos grabado una serie de 10 partes de [Azure ExpressRoute para Office 365 Training](https://channel9.msdn.com/series/aer) en Channel 9 para ayudar a explicar los conceptos de forma más exhaustiva.

## <a name="what-office-365-services-are-included"></a>¿Qué servicios Office 365 se incluyen?
<a name="BKMK_WhatDoIGet"> </a>

En la tabla siguiente se enumeran los servicios de Office 365 que se admiten a través de ExpressRoute. Revise el [artículo puntos de conexión de Office 365](./urls-and-ip-address-ranges.md) para comprender qué solicitudes de red para estas aplicaciones requieren conectividad a Internet.

| Aplicaciones incluidas |
|:-----|
|Exchange Online <sup>1</sup> <br/> Exchange Online Protection <sup>1</sup> <br/> Delve <sup>1</sup> <br/> |
|Skype Empresarial Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive para la Empresa <sup>1</sup> <br/> Project Online <sup>1</sup> <br/> |
|Portal y<sup>compartido 1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Conectar <sup>1</sup> <br/> Office <sup>1</sup> <br/> |

<sup>1</sup> Cada una de estas aplicaciones tiene requisitos de conectividad a Internet no admitidos a través de ExpressRoute; consulte el [artículo puntos de conexión de Office 365](./urls-and-ip-address-ranges.md) para obtener más información.

Los servicios que no se incluyen con ExpressRoute para Office 365 son Aplicaciones Microsoft 365 para empresas descargas de cliente, inicio de sesión del proveedor de identidades local y servicio de Office 365 (operado por 21 Vianet) en China.

## <a name="implementing-expressroute-for-office-365"></a>Implementar ExpressRoute para Office 365

La implementación de ExpressRoute requiere la participación de los propietarios de la red y de la aplicación y requiere una planeación cuidadosa para determinar la nueva [arquitectura de enrutamiento de red](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), los requisitos de ancho de banda, dónde se implementará la seguridad, la alta disponibilidad, etc. Para implementar ExpressRoute, deberá hacer lo siguiente:

1. Comprenda completamente la necesidad que ExpressRoute satisface en el planeamiento de conectividad de Office 365. Comprenda qué aplicaciones usarán Internet o ExpressRoute y planee completamente la capacidad de red, la seguridad y las necesidades de alta disponibilidad en el contexto del uso de Internet y ExpressRoute para Office 365 tráfico.

2. Determine las ubicaciones de salida y emparejamiento para internet y el tráfico de ExpressRoute<sup>1</sup>.

3. Determine la capacidad necesaria en las conexiones de Internet y ExpressRoute.

4. Tenga un plan para implementar la seguridad y otros controles perimetrales estándar<sup>1</sup>.

5. Tener una cuenta de Microsoft Azure válida para suscribirse a ExpressRoute.

6. Seleccione un modelo de conectividad y un [proveedor aprobado](/azure/expressroute/expressroute-locations). Tenga en cuenta que los clientes pueden seleccionar varios modelos de conectividad o asociados y el asociado no tiene que ser el mismo que el proveedor de red existente.

7. Valide la implementación antes de dirigir el tráfico a ExpressRoute.

8. Opcionalmente [, implemente QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) y evalúe la expansión regional.

<sup>1</sup> Consideraciones importantes sobre el rendimiento. Las decisiones aquí pueden afectar considerablemente a la latencia, que es fundamental para aplicaciones como Skype Empresarial.

Para obtener referencias adicionales, use nuestra [guía de enrutamiento](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) además de la [documentación de ExpressRoute](/azure/expressroute/expressroute-introduction).

Para comprar ExpressRoute para Office 365, deberá trabajar con uno o varios [proveedores aprobados](/azure/expressroute/expressroute-locations) para aprovisionar los circuitos de número y tamaño deseados con una suscripción de ExpressRoute Premium. No hay licencias adicionales para comprar en Office 365.

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/expressrouteoffice365]()

¿Está listo para registrarse en [ExpressRoute para Office 365](https://aka.ms/ert)?

## <a name="related-topics"></a>Temas relacionados

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)

[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)

[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)

[Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)

[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)

[Uso de comunidades BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md)

[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)

## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
