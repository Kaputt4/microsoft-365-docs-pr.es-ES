---
title: Microsoft 365 Servicios de ubicación de conectividad de red
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Servicios de ubicación de conectividad de red
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470453"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Servicios de ubicación de conectividad de red

El Centro Microsoft 365 administración muestra ahora Información de red y recomendaciones de rendimiento, que son **métricas** de rendimiento en directo que se recopilan desde el Microsoft 365 inquilino. Estas métricas solo las pueden ver los usuarios administrativos del espacio empresarial. La conectividad de red organizativa se diseña por ubicación de oficina a través de una ubicación de salida de red a Internet. Microsoft 365 la conectividad de cliente usa esa ruta y, a continuación, a través de Internet a los servidores de puerta principal del servicio de Microsoft. La identificación de ubicaciones de oficina es clave para poder mostrar estos conocimientos de red.

## <a name="location-in-network-measurements"></a>Ubicación en las medidas de red

El administrador de una organización puede optar por que la ubicación se incluya en las medidas de red usadas por esta característica. Esto permite la detección automática de la ciudad donde se encuentra cada oficina. La información de ubicación no es precisa y se oculta a 300 m y se clasifica por ciudad. En el momento en que se captura la ubicación en  un Windows, el dispositivo mostrará un icono Ubicación en uso en la bandeja de herramientas. Es posible que los administradores quieran notificar a los usuarios la apariencia de este icono. Con este procesamiento, la ubicación se trata como la ubicación de la oficina de la organización y no la ubicación de una persona o un dispositivo. Los conocimientos de red se pueden mostrar en estas ciudades de ubicación de oficina detectadas. Si desea una mayor precisión en las recomendaciones, puede especificar direcciones de ubicación de oficina específicas. En su lugar, la información de red se agregará a esas ubicaciones. Office no se pueden agregar más de 300 metros.

## <a name="location-in-the-microsoft-365-admin-center"></a>Ubicación en el Centro Microsoft 365 administración

En el Centro Microsoft 365 administración, Bing controles de mapa se usan para mostrar dónde están las ubicaciones de oficina de la organización. Los controles también muestran la topología perimetral de red para una ubicación de oficina seleccionada. Cuando un administrador agrega detalles de direcciones específicos para las ubicaciones de oficina, mapas de Bing también se usa para sugerir direcciones para facilitar la entrada de datos.

## <a name="terms-of-use"></a>Condiciones de uso

Cualquier contenido proporcionado a mapas de Bing, incluidos los geocódigos, solo se puede usar dentro del producto a través del cual se proporciona el contenido. El uso por parte del cliente de la característica de servicios de ubicación del Centro de administración de Microsoft 365, con tecnología de mapas de Bing, se rige por los Términos de uso de _mapas de Bing End-User_ disponibles en y la Declaración de privacidad de <https://go.microsoft.com/?linkid=9710837> [Microsoft](https://go.microsoft.com/fwlink/?LinkID=248686).

Esta característica, que se proporciona mapas de Bing, también es compatible con **TomTom**. Encontrará más información sobre los productos y servicios de TomTom en [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro Microsoft 365 administración (versión preliminar)](office-365-network-mac-perf-overview.md)

[Microsoft 365 de rendimiento de red (versión preliminar)](office-365-network-mac-perf-insights.md)

[Microsoft 365 de red (versión preliminar)](office-365-network-mac-perf-score.md)

[Microsoft 365 de conectividad en el Centro Microsoft 365 administración (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)
