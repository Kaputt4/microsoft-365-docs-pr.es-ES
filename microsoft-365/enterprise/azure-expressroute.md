---
title: Azure ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: Obtenga información sobre cómo usar Azure ExpressRoute con Office 365 y planear el proyecto de implementación de red si va a implementar con él.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693614"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Obtenga información sobre cómo se usa Azure ExpressRoute con Office 365 y cómo planear el proyecto de implementación de red que será necesario si va a implementar Azure ExpressRoute para su uso con Office 365. Los servicios de infraestructura y plataforma que se ejecutan en Azure a menudo se beneficiarán de las consideraciones de rendimiento y arquitectura de red. Recomendamos ExpressRoute para Azure en estos casos. Las ofertas de software como servicio, como Office 365 y Dynamics 365, se han creado para tener acceso de forma segura y confiable a través de Internet. Puede leer sobre el rendimiento y la seguridad de Internet y cuándo puede considerar Azure ExpressRoute para Office 365 en el artículo Evaluación de la conectividad de red de [Office 365.](assessing-network-connectivity.md)

> [!NOTE]
> Se requiere autorización de Microsoft para usar ExpressRoute para Office 365. Microsoft revisa todas las solicitudes de los clientes y autoriza el uso de ExpressRoute para Office 365 cuando el requisito normativo de un cliente exige conectividad directa. Si tiene estos requisitos, proporcione el extracto de texto y el vínculo web al reglamento que interpreta para significar que se requiere conectividad directa en el formulario de solicitud de ExpressRoute para [Office 365](https://aka.ms/O365ERReview) para comenzar una revisión de Microsoft. Las suscripciones no autorizadas que intentan crear filtros de ruta para Office 365 recibirán un [mensaje de error.](https://support.microsoft.com/kb/3181709)

Ahora puede agregar una conexión de red directa a Office 365 para el tráfico de red de Office 365 seleccionado. Azure ExpressRoute ofrece una conexión directa, un rendimiento predecible e incluye un SLA de tiempo de actividad del 99,95 % para los componentes de red de Microsoft. Seguirá necesitando una conexión a Internet para los servicios que no son compatibles con Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Planear Azure ExpressRoute para Office 365

Además de la conectividad a Internet, puede elegir enrutar un subconjunto de su tráfico de red de Office 365 a través de una conexión directa que ofrece previsibilidad y un SLA de tiempo de actividad del 99,95 % para los componentes de red de Microsoft. Azure ExpressRoute le proporciona esta conexión de red dedicada a Office 365 y otros servicios en la nube de Microsoft.

Independientemente de si tiene una WAN de MPLS existente, ExpressRoute se puede agregar a la arquitectura de red de una de estas tres maneras; a través de un proveedor de ubicación co-ubicación de exchange en la nube compatible, un proveedor de conexiones punto a punto Ethernet o a través de un proveedor de conexiones MPLS. Vea qué [proveedores están disponibles en su región.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) La conexión directa de ExpressRoute habilitará la conectividad a las aplicaciones que se describen en ¿Qué servicios de [Office 365 se incluyen? a continuación.](azure-expressroute.md#BKMK_WhatDoIGet) El tráfico de red de todas las demás aplicaciones y servicios seguirá a través de Internet.

Considere el siguiente diagrama de red de alto nivel que muestra un cliente de Office 365 típico que se conecta a los centros de datos de Microsoft a través de Internet para obtener acceso a todas las aplicaciones de Microsoft, como Office 365, Windows Update y TechNet. Los clientes usan una ruta de red similar independientemente de si se conectan desde una red local o desde una conexión a Internet independiente.

![Conectividad de red de Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Ahora, vea el diagrama actualizado que muestra un cliente de Office 365 que usa Internet y ExpressRoute para conectarse a Office 365. Observe que algunas conexiones como dns público y nodos de red de entrega de contenido aún requieren la conexión a Internet pública. Observe también que los usuarios del cliente que no están ubicados en su edificio conectado a ExpressRoute se conectan a través de Internet.

![Conectividad de Office 365 con ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

¿Sigues deseando más información? Obtenga información sobre cómo administrar el tráfico de red con Azure ExpressRoute para [Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) y aprenda a configurar [Azure ExpressRoute para Office 365.](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) También hemos grabado una serie de aprendizaje de Azure ExpressRoute para [Office 365](https://channel9.msdn.com/series/aer) de 10 partes en Channel 9 para ayudar a explicar los conceptos de forma más exhaustiva.

## <a name="what-office-365-services-are-included"></a>¿Qué servicios de Office 365 se incluyen?
<a name="BKMK_WhatDoIGet"> </a>

En la tabla siguiente se enumeran los servicios de Office 365 compatibles con ExpressRoute. Revise el artículo de puntos de conexión de [Office 365](https://aka.ms/o365endpoints) para comprender qué solicitudes de red para estas aplicaciones requieren conectividad a Internet.

|**Aplicaciones incluidas**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype Empresarial Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive para la Empresa<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portal y compartido<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> Cada una de estas aplicaciones tiene requisitos de conectividad a Internet no admitidos en ExpressRoute, consulte el artículo de puntos de conexión de [Office 365](https://aka.ms/o365endpoints) para obtener más información.

Los servicios que no se incluyen con ExpressRoute para Office 365 son las descargas de clientes de Aplicaciones de Microsoft 365 para empresas, el inicio de sesión del proveedor de identidades local y el servicio de Office 365 (operado por 21 Vianet) en China.

## <a name="implementing-expressroute-for-office-365"></a>Implementar ExpressRoute para Office 365

La implementación de ExpressRoute requiere la participación de los propietarios de redes y aplicaciones y requiere una planeación cuidadosa para determinar la nueva arquitectura de enrutamiento de [red,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)los requisitos de ancho de banda, dónde se implementará la seguridad, la alta disponibilidad, entre otros. Para implementar ExpressRoute, tendrá que:

1. Comprenda perfectamente la necesidad que ExpressRoute satisface en la planeación de conectividad de Office 365. Comprenda qué aplicaciones usarán Internet o ExpressRoute y planee completamente sus necesidades de capacidad de red, seguridad y alta disponibilidad en el contexto de usar tanto Internet como ExpressRoute para el tráfico de Office 365.

2. Determine las ubicaciones de salida y emparejamiento para el tráfico de Internet y ExpressRoute<sup>1.</sup>

3. Determine la capacidad necesaria en las conexiones de Internet y ExpressRoute.

4. Tener un plan para implementar la seguridad y otros controles perimetrales estándar<sup>1</sup>.

5. Tener una cuenta válida de Microsoft Azure para suscribirse a ExpressRoute.

6. Seleccione un modelo de conectividad y un [proveedor aprobado.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) Ten en cuenta que los clientes pueden seleccionar varios modelos o partners de conectividad y el partner no necesita ser el mismo que el proveedor de red existente.

7. Valide la implementación antes de dirigir el tráfico a ExpressRoute.

8. [Opcionalmente, implemente QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) y evalúe la expansión regional.

<sup>1 Consideraciones</sup> importantes sobre el rendimiento. Las decisiones aquí pueden afectar considerablemente a la latencia, lo que es fundamental para aplicaciones como Skype Empresarial.

Para obtener referencias adicionales, use nuestra [guía de enrutamiento](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) además de la documentación de [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)

Para comprar ExpressRoute para Office 365, deberá trabajar [](https://azure.microsoft.com/documentation/articles/expressroute-locations/) con uno o más proveedores aprobados para aprovisionar el número y los circuitos de tamaño deseados con una suscripción de ExpressRoute Premium. No hay licencias adicionales para comprar en Office 365.

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

¿Está listo para registrarse en [ExpressRoute para Office 365?](https://aka.ms/ert)

## <a name="related-topics"></a>Temas relacionados

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)

[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)

[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)

[Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)

[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)

[Uso de comunidades de BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md)

[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)

## <a name="see-also"></a>Vea también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
