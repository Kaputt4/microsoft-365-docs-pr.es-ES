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
description: Obtenga información sobre cómo usar Azure ExpressRoute con Office 365 y planear el proyecto de implementación de red si está implementando con él.
ms.openlocfilehash: c43957435272e1a3b6f738d33a2dd12e81dfc013
ms.sourcegitcommit: aff2331f9a3f22591f8ace1a646809969d28c120
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52464422"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Obtenga información sobre cómo se usa Azure ExpressRoute con Office 365 y cómo planear el proyecto de implementación de red que será necesario si va a implementar Azure ExpressRoute para su uso con Office 365. Los servicios de infraestructura y plataforma que se ejecutan en Azure suelen beneficiarse al abordar las consideraciones de rendimiento y arquitectura de red. Se recomienda ExpressRoute para Azure en estos casos. Las ofertas de software como servicio como Office 365 y Dynamics 365 se han creado para tener acceso de forma segura y confiable a través de Internet. Puede leer sobre el rendimiento y la seguridad de Internet y cuándo puede considerar Azure ExpressRoute para Office 365 en el artículo [Assessing Office 365 network connectivity](assessing-network-connectivity.md).

> [!NOTE]
> Microsoft Defender para endpoint no proporciona integración con Azure ExpressRoute. Aunque esto no impedirá que los clientes definan reglas de ExpressRoute que permitan la conectividad desde una red privada a Microsoft Defender para los servicios en la nube de Endpoint, el cliente debe mantener las reglas a medida que evolucione la infraestructura del servicio o la nube.

> [!NOTE]
> No recomendamos ExpressRoute para Microsoft 365 porque no proporciona el mejor modelo de conectividad para el servicio en la mayoría de las circunstancias. Por lo tanto, se requiere autorización de Microsoft para usar este modelo de conectividad para Microsoft 365. Revisamos todas las solicitudes de cliente y autorizamos ExpressRoute para Microsoft 365 solo en los escenarios excepcionales en los que es necesario. Lea la guía de [ExpressRoute](https://aka.ms/erguide) para Microsoft 365 para obtener más información y después de una revisión exhaustiva del documento con los equipos de productividad, red y seguridad, trabaje con el equipo de la cuenta microsoft para enviar una excepción si es necesario. Las suscripciones no autorizadas que intenten crear filtros de Office 365 recibirán un [mensaje de error](https://support.microsoft.com/kb/3181709).

## <a name="planning-azure-expressroute-for-office-365"></a>Planeación de Azure ExpressRoute para Office 365

Además de la conectividad a Internet, puede elegir enrutar un subconjunto del tráfico de red de Office 365 a través de una conexión directa que ofrece previsibilidad y un SLA de tiempo de actividad del 99,95 % para los componentes de red de Microsoft. Azure ExpressRoute le proporciona esta conexión de red dedicada a Office 365 y otros servicios en la nube de Microsoft.

Independientemente de si tiene una WAN de MPLS existente, ExpressRoute se puede agregar a la arquitectura de red de una de tres maneras; a través de un proveedor de ubicación en la nube compatible, un proveedor de conexiones ethernet punto a punto o a través de un proveedor de conexiones MPLS. Vea qué [proveedores están disponibles en su región](/azure/expressroute/expressroute-locations). La conexión directa de ExpressRoute habilitará la conectividad a las aplicaciones descritas [en ¿Qué Office 365 se incluyen? a continuación.](azure-expressroute.md#BKMK_WhatDoIGet) El tráfico de red de todas las demás aplicaciones y servicios seguirá recorriendo Internet.

Tenga en cuenta el siguiente diagrama de red de alto nivel que muestra un cliente de Office 365 típico que se conecta a los centros de datos de Microsoft a través de Internet para obtener acceso a todas las aplicaciones de Microsoft, como Office 365, Windows Update y TechNet. Los clientes usan una ruta de acceso de red similar independientemente de si se conectan desde una red local o desde una conexión a Internet independiente.

![Office 365 de red](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Ahora vea el diagrama actualizado que muestra un cliente Office 365 que usa Internet y ExpressRoute para conectarse a Office 365. Tenga en cuenta que algunas conexiones como DNS público y Content Delivery Network nodos siguen necesitando la conexión pública a Internet. Observe también que los usuarios del cliente que no están ubicados en su edificio conectado a ExpressRoute se conectan a través de Internet.

![Office 365 conectividad con ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

¿Todavía quiere más información? Obtenga información sobre cómo administrar el tráfico de red con [Azure ExpressRoute](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para Office 365 y obtenga información sobre cómo configurar [Azure ExpressRoute para Office 365](/azure/expressroute/expressroute-faqs). También hemos grabado una serie de aprendizaje de [Azure ExpressRoute](https://channel9.msdn.com/series/aer) para Office 365 de 10 partes en channel 9 para ayudar a explicar los conceptos de forma más exhaustiva.

## <a name="what-office-365-services-are-included"></a>¿Office 365 se incluyen los servicios de Office 365?
<a name="BKMK_WhatDoIGet"> </a>

En la tabla siguiente se enumeran los Office 365 que se admiten a través de ExpressRoute. Revise el artículo [Office 365 endpoints para](./urls-and-ip-address-ranges.md) comprender qué solicitudes de red para estas aplicaciones requieren conectividad a Internet.

| Aplicaciones incluidas |
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype Empresarial Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive para la Empresa<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portal y compartido<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Conectar<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> Cada una de estas aplicaciones tiene requisitos de conectividad a Internet que no se admiten en ExpressRoute, consulte el artículo [Office 365 endpoints para](./urls-and-ip-address-ranges.md) obtener más información.

Los servicios que no se incluyen con ExpressRoute para Office 365 son descargas de cliente de Aplicaciones Microsoft 365 para empresas, inicio de sesión del proveedor de identidades local y servicio de Office 365 (operado por 21 Vianet) en China.

## <a name="implementing-expressroute-for-office-365"></a>Implementar ExpressRoute para Office 365

La implementación de ExpressRoute requiere la implicación de los propietarios de aplicaciones y redes y requiere una planeación cuidadosa para determinar la nueva arquitectura de enrutamiento de [red,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)los requisitos de ancho de banda, dónde se implementará la seguridad, alta disponibilidad, entre otros. Para implementar ExpressRoute, deberás:

1. Comprenda completamente la necesidad que ExpressRoute satisface en su Office 365 de conectividad. Comprenda qué aplicaciones usarán Internet o ExpressRoute y planee completamente sus necesidades de capacidad de red, seguridad y alta disponibilidad en el contexto del uso de Internet y ExpressRoute para el tráfico Office 365 red.

2. Determine la salida y las ubicaciones de emparejamiento para el tráfico de Internet y ExpressRoute<sup>1</sup>.

3. Determine la capacidad necesaria en las conexiones de Internet y ExpressRoute.

4. Tener un plan para implementar la seguridad y otros controles perimetrales estándar<sup>1</sup>.

5. Tener una cuenta Microsoft Azure para suscribirse a ExpressRoute.

6. Seleccione un modelo de conectividad y un [proveedor aprobado.](/azure/expressroute/expressroute-locations) Tenga en cuenta que los clientes pueden seleccionar varios modelos o partners de conectividad y el partner no necesita ser el mismo que el proveedor de red existente.

7. Valide la implementación antes de dirigir el tráfico a ExpressRoute.

8. [Opcionalmente, implemente QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) y evalúe la expansión regional.

<sup>1 Consideraciones</sup> de rendimiento importantes. Las decisiones aquí pueden afectar considerablemente a la latencia, lo que es fundamental para aplicaciones como Skype Empresarial.

Para obtener referencias adicionales, use nuestra [guía de enrutamiento](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) además de la documentación de [ExpressRoute](/azure/expressroute/expressroute-introduction).

Para comprar ExpressRoute para Office 365, deberá trabajar con uno [](/azure/expressroute/expressroute-locations) o más proveedores aprobados para aprovisionar los circuitos de número y tamaño deseados con una suscripción Premium ExpressRoute. No hay licencias adicionales para comprar en Office 365.

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/expressrouteoffice365]()

¿Listo para registrarse en [ExpressRoute para Office 365?](https://aka.ms/ert)

## <a name="related-topics"></a>Temas relacionados

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)

[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)

[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)

[Planeamiento de red con ExpressRoute para Office 365](network-planning-with-expressroute.md)

[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)

[Uso de comunidades BGP en ExpressRoute para Office 365 escenarios](bgp-communities-in-expressroute.md)

[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)

[Intervalos de direcciones IP y URL de Office 365](urls-and-ip-address-ranges.md)

[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)

## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
