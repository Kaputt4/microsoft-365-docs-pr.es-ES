---
title: Servicios de ubicación de conectividad de red de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/06/2021
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
ms.custom: admindeeplinkMAC
description: Servicios de ubicación de conectividad de red de Microsoft 365
ms.openlocfilehash: 9900a26441111dc3d2aeb5e589e9a1aa22ed703c
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68198303"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Servicios de ubicación de conectividad de red de Microsoft 365

El <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> ahora muestra **Network Insights y las recomendaciones de rendimiento**, que son métricas de rendimiento en directo que se recopilan de su inquilino de Microsoft 365. Estas métricas solo las pueden ver los usuarios administrativos del inquilino. La conectividad de red de la organización está diseñada por ubicación de oficina a través de una ubicación de salida de red a Internet. La conectividad de cliente de Microsoft 365 usa esa ruta y, a continuación, a través de Internet a los servidores de puerta de servicio de Microsoft. La identificación de las ubicaciones de office es clave para poder mostrar estas conclusiones de red.

## <a name="location-in-network-measurements"></a>Ubicación en las medidas de red

El administrador de una organización puede optar por que la ubicación se incluya en las medidas de red que usa esta característica. Esto permite la detección automática de la ciudad donde se encuentra cada oficina. La información de ubicación no es precisa y se ofusca a 300m y se clasifica por ciudad. En el momento en que se captura la ubicación en un dispositivo Windows, el dispositivo mostrará un icono **Ubicación en uso** en la bandeja de herramientas. Es posible que los administradores quieran notificar a los usuarios la apariencia de este icono. Con este procesamiento, la ubicación se trata como la ubicación de la oficina de la organización y no como la ubicación de una persona o un dispositivo. La información de red se puede mostrar en estas ciudades de ubicación de oficina detectadas. Si desea una mayor precisión en las recomendaciones, puede especificar direcciones de ubicación de oficina específicas. En su lugar, la información de red se agregará a esas ubicaciones. Las ubicaciones de Office no se pueden agregar más de 300 metros.

## <a name="location-in-the-microsoft-365-admin-center"></a>Ubicación en el Centro de Administración de Microsoft 365

En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, los controles de mapa de Bing se usan para mostrar dónde están las ubicaciones de la oficina de la organización. Los controles también muestran la topología perimetral de red para una ubicación de oficina seleccionada. Cuando un administrador agrega detalles de direcciones específicos para las ubicaciones de office, mapas de Bing también se usa para sugerir direcciones para facilitar la entrada de datos.

## <a name="terms-of-use"></a>Condiciones de uso

Cualquier contenido proporcionado a través de mapas de Bing, incluidos los geocódigos, solo se puede usar dentro del producto a través del cual se proporciona el contenido. El uso por parte del cliente de la característica <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> Location Services, con tecnología de mapas de Bing, se rige por los _términos de uso de mapas de Bing End-User_ disponibles en <https://go.microsoft.com/?linkid=9710837> y la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?LinkID=248686).

Esta característica, proporcionada a través de mapas de Bing, también es compatible con **TomTom**. Puede encontrar más información sobre los productos y servicios de TomTom en [https://www.tomtom.com/legal](https://www.tomtom.com/legal).

## <a name="related-topics"></a>Temas relacionados

[Conectividad de red en el Centro de Administración de Microsoft 365](office-365-network-mac-perf-overview.md)

[Información sobre el rendimiento de red de Microsoft 365](office-365-network-mac-perf-insights.md)

[Evaluación de red de Microsoft 365](office-365-network-mac-perf-score.md)

[Prueba de conectividad de Microsoft 365 en el Centro de administración de Microsoft 365](office-365-network-mac-perf-onboarding-tool.md)
